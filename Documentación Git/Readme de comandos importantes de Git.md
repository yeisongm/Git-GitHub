
# Lo siguiente es una documentación del curso de Git - GitHub en Platzi

### CONCEPTOS 📒

#### ¿QUÉ ES GIT?
Git es un sistema de control de versiones distribuido que te permite registrar los cambios que haces en tus archivos y volver a versiones anteriores si algo sale mal. Fue diseñado por Linus Torvalds para garantizar la eficiencia y confiabilidad del mantenimiento de versiones de aplicaciones que tienen un gran número de archivos de código fuente.

#### CARACTERÍSTICAS DE GIT
- Git almacena la información como un conjunto de archivos.
- Casi todo en Git es local. Es difícil que se necesiten recursos o información externos, basta con los recursos locales con los que cuenta.
- Git cuenta con 3 estados en los que podemos localizar nuestros archivos: **Staged**, **Modified** y **Committed**.

#### GITHUB
GitHub es un servicio de alojamiento que ofrece a los desarrolladores repositorios de software usando el sistema de control de versiones, Git.

#### CARACTERÍSTICAS DE GITHUB
- Es la opción perfecta para poder trabajar en equipo en un mismo proyecto.
- Ofrece todas las ventajas del sistema de control de versiones Git, pero también tiene otras herramientas que ayudan a tener un mejor control de nuestros proyectos.

#### REPOSITORIO REMOTO
Un repositorio remoto es un lugar en internet donde almacenamos nuestro repositorio para que no solo viva en local sino que cualquier persona del equipo (que tenga permisos) pueda verlo y contribuir a nuestro proyecto entre otras cosas mas. Estos repositorios remotos facilitan el trabajo colaborativo puesto que cada uno de los integrantes de nuestro equipo podrá entrar y ver los cambios hechos, aportar a estos cambios y demas cosas.

Estos servidores remotos pueden estar alojados en **GitHub**, **GitLab**, **BitBucket**, entre otros. Lo que van a hacer es guardar el mismo repositorio que tienes en tu computadora y darnos una URL con la que todos podremos acceder a los archivos del proyecto. Así, el equipo podrá descargarlos, hacer cambios y volverlos a enviar al servidor remoto para que otras personas vean los cambios, comparen sus versiones y creen nuevas propuestas para el proyecto.

#### LLAVES PÚBLICAS Y PRIVADAS
Las llaves públicas y privadas, conocidas también como cifrado asimétrico de un solo camino, sirven para mandar mensajes privados entre varios nodos con la lógica de que firmas tu mensaje con una llave pública vinculada con una llave privada que puede leer el mensaje.

Las llaves públicas y privadas nos ayudan a cifrar y descifrar nuestros archivos de forma que los podamos compartir sin correr el riesgo de que sean interceptados por personas con malas intenciones.

* #### **¿Cómo funciona un mensaje cifrado con llaves públicas y privadas?**
    1. Ambas personas deben crear su llave pública y privada.
    2. Ambas personas pueden compartir su llave pública a las otras partes (recuerda que esta llave es pública, no hay problema si la “interceptan”).
    3. La persona que quiere compartir un mensaje puede usar la llave pública de la otra persona para cifrar los archivos y asegurarse que solo puedan ser descifrados con la llave privada de la persona con la que queremos compartir el mensaje.
    4. El mensaje está cifrado y puede ser enviado a la otra persona sin problemas en caso de que los archivos sean interceptados.
    5. La persona a la que enviamos el mensaje cifrado puede emplear su llave privada para descifrar el mensaje y ver los archivos.

    _Nota: puedes compartir tu llave pública, pero nunca tu llave privada._

---

### COMANDOS ⌨️

#### UBICACIÓN ACTUAL DEL USUARIO EN LA PC
El siguiente comando nos muestra la ubicación (path) del directorio actual de trabajo:
```
    pwd
```

#### CREAR REPOSITORIOS
Para iniciar u obtener un nuevo repositorio, usaremos los siguientes comandos: 

|COMANDO|DESCRIPCIÓN|
|:------|:----------|
|`git init`|Crea un nuevo repositorio local.|
|`git init <projectName>`|Crea un nuevo repositorio con el nombre especificado.|
|`git clone <url>`|Descarga un proyecto y toda su historia de versión.|

Con el comando `init` se crea un area en memoria RAM llamada **staging** que está completamente desconectada. Pero a su vez se crea el repositorio local (carpeta llamada **.git**).

#### AGREGAR ARCHIVOS
Necesitamos agregar al staged los archivos que queremos proteger, así que lo haremos con el comando add:
```
    git add <file>
```
Cuando ejecutamos este comando, se guardan todos los cambios en el **staging** y los archivos pasan a estado **tracked**.
Pero si modificamos el archivo, debemos ejecutar nuevamente este comando porque el archivo.

> [!NOTE]
> _Nota 1: si el nombre del archivo tiene espacios, usa comillas simples. Ejemplo:_
``` 
    git add 'Comandos importantes.txt' 
```
>[!NOTE]
>_Nota 2: Cuando no se ha ejecutado este comando a un archivo, se encuentra en estado **untracked** o sin rastrear._


#### BORRAR ARCHIVO AGREGADO
Si agregamos un archivo y deseamos borrarlo, usaremos el siguiente comando:

|COMANDO                 |DESCRIPCIÓN                                    |
|:-----------------------|:----------------------------------------------|
|`git rm <file>`         |Elimina el archivo de **git** sin eliminar su historial del sistema de versiones.             |
|`git rm --cached <file>`|Elimina el archivo de **staging** y el próximo **commit**. Pero los mantiene en el disco duro.|
|`git rm --force <file>`|Elimina los archivos de **git** y el disco duro.|

#### ENVIAR LOS CAMBIOS AGREGADOS AL REPOSITORIO
Luego de agregar los archivos, si queremos enviarlos al repositorio, podemos usar los siguientes comandos:

|COMANDO                     |DESCRIPCIÓN                       |
|:---------------------------|:---------------------------------|
|`git commit -m "<message>"` |Enviar los cambios al repositorio.|
|`git commit -am "<message>"`|Realiza el `git add` y el `git commit` en un solo comando.|

Cuando ejecutamos este comando, estamos enviando los cambios al repositorio (**.git**), que a su vez tiene un nombre por defecto y es **master**.

>[!NOTE]
> _Nota: Si hacemos un **commit** sin mensaje, git nos lanzará a una pantalla donde solo podremos salir si escribirmos el mensaje y presionamos las teclas `Esc + Shift + Z + Z`, con el comando anterior forzamos el envio del **commit** porque guarda el archivo. Esto en VIM se conoce como guardar._

#### VER ESTADO DE LOS CAMBIOS
Para ver los cambios que se han hecho usamos el siguiente comando:
```
    git status
```

#### VER HISTORIAL
|COMANDO          |DESCRIPCIÓN                                      |
|:----------------|:------------------------------------------------|
|`git show`       |Ver los cambios que han existido sobre los últimos **commit**s.|
|`git show <file>`|Ver los cambios que han existido sobre los últimos **commit**s de un archivo.|
|`git log <file>` |Ver los ID de los **commit**s.                   |
|`git log --graph --oneline`|Es un pequeño resumen del comando `git log` resumido en una linea.|
|`git diff <idCommitA> <idCommitB>`|Ver diferencia entre una versión y otra especificamente|

#### SUBIR CAMBIOS A UN SERVIDOR REMOTO (GITHUB)
Luego de haber implementado los comandos `add` para agregar y `commit -m` para confirmar, debemos usar otro para subir los cambios a un servidor remoto. El comando es el siguiente:
```
    git push
```
Al enviar los cambios al servidor remoto debemos poner el nombre de la rama remota a la que van dirigidos los cambios, y tambien debemos poner el nombre de la rama local de donde provienen los cambios. El siguiente comando lo explica:
```
    git push <remoteBranch> <localBranch>
    Ejemplo: git push origin master
```

#### CONFIGURACIÓN DE VARIABLES DE ENTORNO
Debemos configurar las variables de entorno para determinar la identidad del que hace los cambios. 
Primero necesitamos visualizar la lista de variables de entorno de Git usando el comando `git config --list` o `git config -l`. Luego de tener la lista visible, necesitamos editar el nombre y correo del usuario, para eso usaremos los siguientes comandos:

|COMANDO                                   |DESCRIPCIÓN                 |
|:-----------------------------------------|:---------------------------|
|`git config --global user.name "<name>"`  |Edita el nombre del usuario.|
|`git config --global user.email "<email>"`|Edita el correo del usuario.|
|`git config --global color.ui auto`       |Habilita la útil colorización de la línea de comando.|

>[!NOTE]
> _Nota: Si no configuramos estas variables de entorno, por defecto apareceran las del sistema operativo actual._

#### CONTENIDO DEL ARCHIVO
Para visualizar el contenido de mi archivo, usamos el comando `cat <file>`.

#### RAMAS (BRANCH)
Cuando se crea un repositorio en la carpeta de trabajo se crea por defecto una rama (**Branch**) principal llamada **master**.
Esta rama principal se puede ver como el mapa lineal de los **commit**s que se han realizados al archivo.

Es muy común entre desarrolladores crear una rama llamada **develop** con la finalidad de hacer pruebas y no tocar la rama principal llamada **master**.

Los sigueintes comandos nos ayudarán con el manejo de las ramas:

|COMANDO                           |DESCRIPCIÓN                           |
|:---------------------------------|:-------------------------------------|
|`git branch`|Ver todas las ramas existentes en nuestro repositorio local.|
|`git branch <branchName>`|Crear nueva rama con un nombre especifico.     |
|`git branch -d <branch>`|Borra la rama especificada.                     |
|`git checkout <branch>`|Cambiar de rama.                                 |
|`git checkout -b <branch>`|Crea una rama y a la vez hace `checkout` a la misma.|

>[!IMPORTANT]
>_Desde el 1 de octubre de 2020 GitHub cambió el nombre de la rama principal: ya no es **“master”** sino **main**. Este derivado de una profunda reflexión ocasionada por el movimiento #BlackLivesMatter. Si se está trabajando desde la rama **master** es necesario pasarse a la rama **main**. Para ello usaremos el comando `git branch -m main`. De esta manera **master** seguirá siendo **main**._

#### REHACER COMMITS
Borrar errores y elaborar historial de reemplazo.

|COMANDO                           |DESCRIPCIÓN                           |
|:---------------------------------|:-------------------------------------|
|`git reset`|Volver en el tiempo sin poder volver al futuro.|
|`git reset <idCommitA> <idCommitB> --hard`|Borra toda la información del area de **staging** y los **commits**. (Se debe tener cuidado con este commando)|
|`git reset <idCommitA> <idCommitB> --soft`|Se borra el historial pero mantiene los archivos del área de **staging** para poder aplicar últimos cambios a un nuevo **commit**.|
|`git reset <idCommitA> <idCommitB> HEAD`|Mueve los cambios de **staging** a **unstaged**. Seguimos teniendo los últimos cambios del archivo, el repositorio sigue teniendo el archivo sólo con los cambios en los que hicimos **commit**.|

#### CAMBIAR DE VERSIONES
Volver a cualquier versión anterior sin borrar el historial del archivo. Se usa el siguiente comando:
```
    git checkout <idCommit>
```

El comando `git checkout` que nos deja ir, mirar, pasear y volver. Con `git reset` volvemos al pasado sin la posibilidad de volver al futuro. Borramos la historia y la debemos sobreescribir. No hay vuelta atrás.

Si queremos movernos atraves de ramas, necesitamos usar los siguientes comandos:

|COMANDO                     |DESCRIPCIÓN                           |
|:---------------------------|:-------------------------------------|
|`git checkout master <file>`|Nos movemos a la rama principal y con los datos más recientes de ese archivo.|
|`git checkout <branch>`     |Nos movemos hacia una rama específica.|

#### GESTIONAR UN REPOSITORIO REMOTO

Para este tema necesitaremos los siguientes comandos:

|COMANDO                     |DESCRIPCIÓN                           |
|:---------------------------|:-------------------------------------|
|`git clone <url_servidor_remoto>`|Nos permite descargar los archivos de la última versión de la rama principal en el repositorio remoto y todo el historial de cambios en la carpeta **.git**.|
|`git push`|Luego de hacer `git add` y `git commit` debemos ejecutar este comando para mandar los cambios al servidor remoto.|
|`git fetch`|Lo usamos para traer actualizaciones del servidor remoto y guardarlas en nuestro repositorio local (en caso de que hayan, por supuesto). Pero no copia la información a mis archivos.|
|`git fetch <branch>`|Descarga cambios del repositorio remoto (GitHub) y crea una rama (branch) que luego se debe fusionar con la rama master de nuestro entorno local.|
|`git merge`|También usamos el comando `git merge` con servidores remotos. Lo necesitamos para combinar los últimos cambios del servidor remoto y nuestro directorio de trabajo. Con este unimos los cambios obtenidos con el `git fetch` a mis archivos.|
|`git merge <branch>`|Fusiona una rama con la actual, que es la misma en donde estamos posicionados. Este `merge` es un `commit` a la rama y necesitará un mensaje, como todos los `commit`.|
|`git pull`|Básicamente, `git fetch` y `git merge` al mismo tiempo.|
|`git pull <branch>`|Descarga cambios del repositorio remoto (GitHub) y fusiona automáticamente la rama especificada a la rama master de nuestro entorno local.|

#### GESTIONAR LLAVES SSH

La creación de las SSH es necesario **solo una vez por cada computadora**. Aquí conocerás cómo conectar a GitHub usando SSH.
Para configurar nuestras llaves SSH en nuestro entorno local, necesitaremos los siguientes comandos:

* #### **Generar una llave SSH:**
    Para generar una clave SSH es muy recomendable estar en el home del repositorio local, para llegar a él podemos hacerlo con el comando `cd ~`.

    Luego podemos crear la clave con el siguiente comando:
    ```
        ssh-keygen -t rsa -b 4096 -C "youremail@example.com"
    ```
    Despues de ejecutar el comando anterior, la consola nos pedirá dónde guardar la llave. Lo recomendable es dejarla en la ruta por defecto, asi que le daremos **ENTER**.

    Finalmente la consola nos pedirá un **passphrase**, el cual es una clave para nuestra llave. Es opcional pero lo recomendable es escribir una.

* #### **Comprobar proceso y agregar la llave:**
    Comprobar que el proceso esté activo y agregar la llave al entorno local:

    |COMANDO                |DESCRIPCIÓN                                        |
    |:----------------------|:--------------------------------------------------|
    |`eval $(ssh-agent -s)`|Comprobar que el servidor de SSH esté activo.       |
    |`ssh-add ~/.ssh/id_rsa`|Agregar la llave al entorno local de windows/LINUX.|

* #### **Vincular las credenciales con SSH:**
    Luego de haber creado las llaves en el home (~), podemos entregarle la llave pública a GitHub para comunicarnos de forma segura y sin necesidad de escribir nuestro usuario y contraseña todo el tiempo. 

    Para hacerlo debemos seguir la siguiente ruta: [`Settings/SSH and GPG keys/New SSH key`](https://github.com/settings/keys), le agregamos el título y en el campo correspondiente pegamos la llave. Finalmente le damos click al botón **Add SSH key**.

#### USO DE GITHUB
Luego de crear nuestra cuenta en [**GitHub**](https://github.com/signup), debemos crear y/o importar nuestro repositorio en [**nuevo repositorio**](https://github.com/new).

Una vez tenemos el nuevo repositorio, debemos conectar con la url de este para dar un origen del remoto al local.
Para esto usamos el siguiente comando:

```
    git remote add origin <url>
```

Luego verificamos que la URL se haya guardado en nuestro entorno local de la siguiente manera:

```
    git remote
    git remote -v
```

Debemos traer la versión del repositorio remoto y hacer **merge** para crear un `commit` con los archivos de ambas partes. Podemos usar `git fetch` y `git merge` o solo el `git pull` de la siguiente manera:

```
    git pull origin main
```

>[!WARNING]
> _Si en la consola aparece alguna advertencia de no haber `commit` comunes (warning: no common `commits`), usaremos el siguiente comando: `git pull origin main --allow-unrelated-histories`._

Por último, debemos hacer `git push` para guardar los cambios de nuestro repositorio local en **GitHub**. Lo haremos usando el siguiente comando:

```
    git push origin main
```

