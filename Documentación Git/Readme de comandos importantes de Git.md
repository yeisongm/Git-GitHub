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


#### CONFIGURAR MÚLTIPLES COLABORADORES EN UN REPOSITORIO DE GITHUB
Por defecto, cualquier persona puede clonar o descargar tu proyecto desde
GitHub, pero no pueden crear commits, ni ramas, ni nada. Para solucionar esto
podemos añadir a cada persona de nuestro equipo como colaborador de nuestro repositorio.
Los pasos son los siguientes:
1. En GitHub, visita la página principal del repositorio.
2. Ir a la configuración del proyecto (**settings**), luego en acceso (**Access**), en colaboradores (**Collaborators**), en administrar acceso (**Manage access**) y darle al botón **Add people**.
3. Procedemos a buscar en el campo de busqueda a la persona que deseamos invitar. Posteriormente damos clic al usuario indicado en la lista de coincidencias. Por ultimo le damos al botón agregar, que dice **Add user to this repository**. El usuario recibirá un email invitándolo al repositorio.

>[!NOTE]
>_Una ruta más corta puede ser **github.com/usuario/repositorio/settings/access**._

Una vez que el colaborador acepte la invitación, tendrá acceso de colaborar en el repositorio.

#### FLUJO DE TRABAJO PROFESIONAL: HACIENDO MERGE DE RAMAS DE DESARROLLO A MASTER.
Para poder desarrollar software de manera óptima y ordenada, necesitamos tener un flujo de trabajo profesional, que nos permita trabajar en conjunto sin interrumpir el trabajo de otros desarrolladores. Una buena práctica de flujo de trabajo sería la siguiente:

1. Crear ramas
2. Asignar una rama a cada programador
3. El programador baja el repositorio con `git pull origin main`.
4. El programador cambia de rama
5. El programador trabaja en esa rama y hace `commit`s
6. El programador sube su trabajo con `git push origin <branchName>`
7. El encargado de organizar el proyecto baja, revisa y unifica todos los cambios con un `git merge <branchName>`.
8. El encargado debe enviar los cambios a GitHub con un `git pull origin main` (obtener los cambios) y un `git push origin main` (envia los cambios).

#### FLUJO DE TRABAJO PROFESIONAL CON PULL REQUESTS
Para realizar pruebas enviamos código a servidores que normalmente los llamamos **staging server**, luego de que se realizan las pruebas pertinentes de código como de la aplicación estos pasan a el **servidor de producción**.

>[!NOTE]
>_En un entorno profesional normalmente se bloquea la rama master, y para enviar código a dicha rama pasa por un code review y luego de su aprobación se unen códigos con los llamados `pull request`._

 * #### **PULL REQUESTS**
    Es la acción de validar un código que se va a mergear de una rama a otra. En este proceso de validación pueden entrar los factores que queramos: Builds (validaciones automáticas), asignación de código a tareas, validaciones manuales por parte del equipo, despliegues, etc.

    >[!NOTE]
    >_Nota: Los `pull request`, no es una caracteristica de Git, si no de Github._

    La persona que hace todo esto, normalmente son los lideres de equipo o un perfil muy especial que se llama DevOps (permite que los roles que antes estaban aislados se coordinen y colaboren para producir productos mejores y más confiables).

    Los `pull request` podrían compararse con un control de calidad interno donde el equipo tiene la oportunidad de detectar bugs o código que no sigue lineamientos, convenciones o buenas prácticas. Incluso puede presentar ahorros a la empresa. Github nos permite llevar un control e implementa un proceso para la atención y revisión de estas solicitudes.

#### UTILIZANDO PULL REQUESTS EN GITHUB
Cuando un desarrollador termina de crear (y probar) ya sea una nueva funcionalidad o corrección de bug, solicita integrar su desarrollo al repositorio principal. Esta solicitud se conoce como pull request (o PR).

>[!NOTE]
>_Nota: No olvidar traer los cambios (Git Pull) y enviar los cambios (Git Push) siempre como buena practica!_

Es una buena práctica crear una nueva rama cada vez que necesitamos corregir un error puntual.

Despues de crear la rama para la corrección del error, haremos lo siguiente:

1. Creamos la branch, solucionamos los problemas, hacemos el commit y subimos los cambios con `git push origin <branchName>`.
2. Cuando subimos los cambios, en github nos aparecerá un mensaje como este _"you recently pushed branches, **branchName** (less than a minute ago) compare & pull request"_ **GitHub nos ofrece comparar la rama con master y hacer un `pull request`**. También hay un botón al lado del de branch que dice `New pull request`.
3. Si soy el/la dueño(a) del repositorio, estoy en la rama master y le doy `pull request` Podré comparar master con otras ramas. De esta manera puedo ver cuales
fueron los cambios (github nos indica si es posible hacer el merge automáticamente.) Nos aparece la opción de agregar **reviewers**.
4. El `pull request` no ejecuta el merge de por sí, simplemente describe que es lo que está pasando. Colocamos los colaboradores que queremos que revisen los cambios y presionamos `create pull request`.
5. La otra persona en su cuenta al entrar al repositorio verá que tiene 1 `pull request` y se le indica quién le ha solicitado revisar los cambios y con qué objetivo (En este caso, fusionar la rama master con fix-typo).
6. El colaborador tiene acceso a los commits y cambios realizados y puede decidir si aceptar los cambios o no. Esto se hace a través de **review changes**. Se pueden aprobar esos cambios (approve), comentar o requerir cambios request changes. En este caso el colaborador pide cambios.
7. Desde mi repositorio local realizo los cambios solicitados, los subo al remoto y en github puedo observar que al lado del nombre de la rama me aparece **View #1** que es el `pull request` que ya había ejecutado. Desde ahí puedo enviarle un mensaje al colaborador y avisarle que ya están los cambios.
8. El colaborador recibe los cambios, los revisa y ya puede decidir si aprobarlos con review changes.
9. Una vez aprobados los cambios no significa que el merge se ejecute, alguien debe hacerlo y para ello es muy importante que esté bien definido quien es la persona encargada. Normalmente el encargado es el administrador o el **DevOps** hace el **merge** con la rama principal.
10. Si se requiere, podemos eliminar la rama ya que fue creada solo para solucionar un error (**Delete Branch**).

>[!NOTE]
>_Una vez realizado el Merge, es importante traer los cambios en Git (**Git Pull**), en caso de querer borrar la rama en GitHub, podemos borrarla en Git con `git branch -D <branchName>`._

#### IGNORAR ARCHIVOS EN EL REPOSITORIO CON .GITIGNORE
Muchos poryectos tienen archivos que no pueden ser públicos, como archivos de configuración con contraseñas, lo ideal es que no se suban al repositorio. Estos archivos se pueden poner en el archivo **.gitignore**.

Las reglas sobre los patrones que puedes incluir en el archivo .gitignore son las siguientes:

* Ignorar las líneas en blanco y aquellas que comiencen con #.
* Aceptar patrones glob estándar.
* Los patrones pueden terminar en barra (/) para especificar un directorio.
* Los patrones pueden negarse si se añade al principio el signo de exclamación (!).

>[!TIP]
>_Tip:Una buena practica es evitar que los archivos binarios del contenido, sean parte del repositorio._

Cuando se crea archivo .gitignore, se debe confirmar con `git add` .gitignore y luego el commit respectivo para que se agregue al repositorio.

#### Ejemplo de un archivo .gitignore por https://gitignoraio/
|REGLA |DESCRIPCIÓN                 |
|:-----|:---------------------------|
|*.a   |# ignora los archivos en . a|
|!lib.a|# pero no lib.a, aun cuando había ignorado los archivos terminados en .a en la línea anterior|
|/TODO|# ignora unicamente el archivo 1000 de la raiz, no subdir/|
|build/|# ignora todos los archivos del directorio build/|
|doc/*.txt|# ignora doc/notes.txt, pero no este: doc/server/arch.txt|
|doc/**/*.txt|# ignora todos los archivos .txt del directorio doc/|

>[!TIP]
>_Es importante que archivo se nombre ".gitignore", con punto al inicio._

.Gitignore sirve para decirle a Git qué archivos o directorios completos debe ignorar y no subir al repositorio de código. Únicamente se necesita crear un archivo especificando qué elementos se deben ignorar y, a partir de entonces, realizar el resto del proceso para trabajo con Git de manera habitual.

#### TU SITIO WEB PÚBLICO CON GITHUB PAGES
Puedes usar Páginas de GitHub para albergar un sitio web sobre ti mismo, organización o proyecto directamente desde un repositorio GitHub. 
Abrirla página oficial de Github para más ayuda: https://pages.github.com/

Para agregar una url de Github Pages a un repositorio existente:
* Ir a **"settings"** del repositorio en la pestaña **"Options"**, en la sección ["**GitHub Pages**"](https://pages.github.com/).
* Elegir en **"Source"**, la rama principal donde se encuentra el código actualizado. Esto genera en automático la Url de la web alojada en Github.

**Github Pages** es vn beneficio adicional que te permite publicar sitio web de forma gratuita y desde la CDN global de Github, basado en una rama que puede ser diferente a la master. La ventaja de esto es que la web se puede actualizar con cambios en el repositorio y Ejecutando un git commit/git push, además de contar con certificado HTTPS para proporcionar mayor transparencia y seguridad para los usuarios.

#### GIT STASH: GUARDAR CAMBIOS EN MEMORIA Y RECUPERARLOS DESPUÉS
El comando `git stash` almacena temporalmente (o guarda en un stash) los cambios que hayas efectuado en el código con el que estás trabajando para que puedas trabajar en otra cosa y, más tarde, regresar y volver a aplicar los cambios.

Git stash es uno de los comandos más útiles de Git. Es una forma rápida de tener en temporal tus cambios, poder moverte entre ramas y luego recuperar esos cambios. **Git stash** se recomienda cuando haces pequeños cambios que no merecen ramas o cuando llevas trabajo adelantado y necesitas datos de otra rama pero no estas listo para hacer commit.

#### GIT CHERRY-PICK: TRAER COMMITS ANTIGUOS AL HEAD DEL BRANCH
`Git cherry-pick` es un comando en Git que selecciona y aplica commits específicos de una rama o branch a otra. Todo, sin tener que hacer un merge completo. Así, podemos copiar un commit específico y aplicarlo de forma aislada en la rama de destino, conservando su historial.

* #### Escenarios de uso de Git Cherry Pick
    Este comando facilita la incorporación precisa de cambios, optimizando la colaboración y el mantenimiento en proyectos de desarrollo de software. Veamos sus casos de uso.

    1. #### Colaboración en equipo
        Antes que nada, puede ser útil implementarlo cuando diferentes miembros del equipo trabajan en áreas similares del código, pues permite seleccionar y aplicar commits específicos a cada rama, facilitando el progreso individual.

    2. #### Solución de bugs o errores
        Cuando encuentras un error o bug, es importante solucionarlo y entregar la corrección a los usuarios lo más rápido posible. Con Git Cherry Pick, puedes aplicar rápidamente un commit de verificación en la rama principal, evitando que afecte a más usuarios.

    3. #### Deshacer cambios y recuperar commits perdidos
        A veces, una rama de funcionalidad puede ser obstoleta y no ser fusionada con la rama principal. O puede suceder que una solicitud de extracción (pull request) sea cerrada sin ser fusionada.

Git nunca pierde esos commits y, a través de comandos como `git log` y `git reflog`, puedes encontrar y aplicar los commits utilizando Git Cherry Pick.

* #### ¿Cómo funciona Git Cherry Pick? Ejemplos
    Imaginemos que tienes un repositorio con el siguiente estado de las ramas:

    ```
    a - b - c - d   Rama Principal
         \\
           e - f - g Rama de Características
    ```

    El uso de Git Cherry Pick es bastante sencillo y se ejecuta de la siguiente manera:

    1. Primero, asegúrate de estar en la rama principal empleando el comando git checkout rama-principal.
    2. Luego, ejecuta el siguiente comando:

    ```
        git cherry-pick <hashCommit>
    ```

    Aquí, commitSha es una referencia al commit que deseas aplicar. Puedes encontrar la referencia del commit utilizando el comando git log. Supongamos que deseas usar el commit ‘f’ en la rama principal.

    Una vez ejecutado el comando, el historial de Git se verá así:

    ```
    a - b - c - d - f   Rama Principal
         \\
           e - f - g Rama de Características
    ```

    De esta forma, el commit ‘f’ se ha incorporado correctamente a la rama principal.

El uso de Git Cherry Pick debería aplicarse con sabiduría, ya que **puede generar duplicación de commits** y **complicaciones en el historial de cambios**. Sin embargo, si sabes lo que estás haciendo, ¡adelante! Solo asegúrate de evitar su utilización si no estás seguro.

* #### ¿Cómo deshacer este comando en caso de conflicto?
    Supongamos que estás usando GitHub para colaborar con un equipo en un proyecto y has realizado un cherry-pick de un commit de otra rama en tu rama local, pero ocurren conflictos durante este proceso y deseas detenerlo y volver al estado anterior.

    Por suerte, en ese caso, puedes emplear el siguiente comando.

    ```
        git cherry-pick --abort
    ```

    Esto significa que puedes hacer las correcciones necesarias en tu rama local y volver a intentar el cherry-pick si así lo deseas.

#### GIT RESET Y REFLOG: ÚSESE EN CASO DE EMERGENCIA
Git guarda todos los cambios aunque decidas borrarlos, al borrar un cambio lo que estás haciendo sólo es actualizar la punta del branch, para gestionar éstas puntas existe un mecanismo llamado registros de referencia o reflogs…La gestión de estos cambios es mediante los hash’es de referencia (o ref) que son apuntadores a los commits…Los recoges registran cuándo se actualizaron las referencias de Git en el repositorio local (sólo en el local), por lo que si deseas ver cómo has modificado la historia puedes utilizar el comando:

```
    git reflog
```

#### RECONSTRUIR COMMITS EN GIT CON AMEND
`Git amend` es una forma que tienes para hacer cambios a tu commit más recientes sin tener que hacer un nuevo commit.

* #### Recomendaciones en el uso de git amend
    El comando de `git amend` se usa para modificar el último commit. Es decir, te permite “revisar” o “corregir” el último cambio confirmado que hayas hecho en tu proyecto.

    Por ejemplo, imagínate que acabas de hacer un commit, pero te diste cuenta de que no querías enviarlo porque faltaba algo más. En lugar de hacer un nuevo commit, puedes usar `git commit --amend` para agregar esos cambios al commit más reciente. Esto es útil porque mantiene tu historial de commits limpio y organizado.

    Usar **amend** es considerado una mala práctica, especialmente después de haber hecho push o pull al repositorio remoto. Al hacer **amend** con algún commit que ya esté en remoto, se generará un conflicto que deberá resolverse con un commit adicional. En este proceso, se perderá el beneficio del **amend**.

    No utilizar **--amend** para reconstruir commits que ya se encuentran en el repositorio remoto. Esto sería una mala práctica.

* #### ¿Cómo hacer un git amend?
    Utilizar **amend** para remendar un commit puede modificar el commit más reciente (enmendar) en la misma rama. Se ejecuta de la siguiente manera:

    ```
        git commit --amend
    ```

* #### ¿Para qué sirve git commit amend?
    Este comando sirve para agregar archivos nuevos o actualizar el commit anterior y no generar commits innecesarios. También es una forma sencilla de editar o agregar comentarios al commit anterior porque abrirá la consola para editar este commit anterior.

Procura no corregir una confirmación en la que otros desarrolladores hayan basado su trabajo, ya que crea una Situación confusa para ellos de la que resulta complicado recuperarse.

>[!CAUTION]
>_No se recomienda 'modificar' un commit ya enviado a un repositorio, pero en caso de que se tenga que volver a enviar, podemos hacerlo adicionando la opción `--force` a `git push`. Posiblemente luego debemos solucionar algún conflicto de forma manual. Tener precaución en su uso. `git pugh origin master --forc`_

#### BUSCAR EN ARCHIVOS Y COMMITS DE GIT CON GREP Y LOG
A medida que nuestro proyecto se va haciendo más grande y este conformado de múltiples archivos, Git nos ofrece herramientas de búsqueda tanto en los directorios de trabajo como en log de confirmaciones. Las opciones se pueden ejecutar combinadas, que lo vuelve una opción muy útil y poderosa para la administxación de nuestro proyecto.

* #### GIT GREP
    Git tiene un comando llamado grep que le permite buscar fácilmente a través de cualquier árbol o directorio de trabajo con commit, por una cadena de texto. Por defecto, comando buscará a través de los archivos en directorio de trabajo.

* #### BUSQUEDA DE REGISTROS CON GIT LOG
    El comando git log tiene varias herramientas potentes para encontrar commits específicos por contenido de sus mensajes o incluso contenido de las diferencias que introducen.

En Git también se pueden realizar búsquedas con expresiones regulares. Las expresiones regulares son patrones que se utilizan para hacer coincidir combinaciones de caracteres en cadenas.

-------------------------------------------------------------------------------

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
|`git log --all --graph --decorate --oneline`|Un resumen del `git log` en forma de grafo decorado y en una sola línea.|
|`git diff <idCommitA> <idCommitB>`|Ver diferencia entre una versión y otra especificamente|

>[!TIP]
>_Existe un comando con el que podemos ver toda la historia de nuestro proyecto en un software y de forma más visual. Este comando es `gitk`._

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

#### GUARDAR COMANDO CON UN ALIAS
Cuando tenemos un comando demasiado largo, dificil de aprender, usamos los alias de linux. Estos alias funcionan como variables en donde almacenamos el comando para usarlo posteriormente.
La manera de usarlos es la siguiente:

```
    alias miVariable = "git log --all --graph --decorate --oneline"
```

#### RAMAS (BRANCH)
Cuando se crea un repositorio en la carpeta de trabajo se crea por defecto una rama (**Branch**) principal llamada **master**.
Esta rama principal se puede ver como el mapa lineal de los **commit**s que se han realizados al archivo.

Es muy común entre desarrolladores crear una rama llamada **develop** con la finalidad de hacer pruebas y no tocar la rama principal llamada **master**.

Los siguientes comandos nos ayudarán con el manejo de las ramas:

|COMANDO                           |DESCRIPCIÓN                           |
|:---------------------------------|:-------------------------------------|
|`git branch`|Ver todas las ramas existentes en nuestro repositorio local.|
|`git branch <branchName>`|Crear nueva rama con un nombre especifico.     |
|`git show-branch`|Ver las ramas existentes de nuestro repositorio local, pero con más detalles.|
|`git show-branch --all`|Ver las ramas existentes, con su ubicación (local o remoto) y su historia más reciente junto a sus commits.|
|`git branch -d <branch>`|Borra la rama especificada.                     |
|`git branch -v`|Listar las ramas locales.|
|`git branch -r`|Listar las ramas remotas.|
|`git branch -a`|Listar todas las ramas locales y remotas.|
|`git checkout <branch>`|Cambiar de rama.                                 |
|`git checkout -b <branch>`|Crea una rama y a la vez hace `checkout` a la misma.|

>[!IMPORTANT]
>_Desde el 1 de octubre de 2020 GitHub cambió el nombre de la rama principal: ya no es **“master”** sino **main**. Este derivado de una profunda reflexión ocasionada por el movimiento #BlackLivesMatter. Si se está trabajando desde la rama **master** es necesario pasarse a la rama **main**. Para ello usaremos el comando `git branch -m main`. De esta manera **master** seguirá siendo **main**._

Se puede trabajar con ramas en local que nunca se envian a GitHub, y viceversa.

* #### **Subir o enviar una rama al repositorio local (GitHub)**
    Las ramas que creamos en nuestro repositorio local no se subirán o crearán en el repositorio remoto, debemos subirlas nosotros mismos.

    >[!IMPORTANT]
    >_No olvidar siempre primero ejecutar el comando `git pull origin main` antes de subir las ramas._

    Para subir nuestra rama usaremos el siguiente comando:

    ```
        `git push origin <nameBranch>`
    ```

    Si queremos subir varias ramas a la vez, usamos el mismo comando anterior pero separando los nombres de las ramas por espacios:

    ```
        `git push origin <branchName1> <branchName2> <branchName3>`
    ```

    >[!NOTE]
    >_Si ya no queremos más una rama remota, la podemos eliminar con el siguiente comando: `git push origin --delete <branchName>`_

    Las ramas en GitHub son importantes porque representan un área de trabajo independiente de desarrollo dentro de nuestro proyecto. Al igual que en nuestro repositorio local, en GitHub podemos trabajar con ramas y nos permiten de la misma manera, traernos los cambios realizados en otras ramas y compararlos para unirlos con nuestros cambios, utilizando Git.


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

#### TAGS Y VERSIONES EN GIT Y GITHUB
Como muchos VCS (Versión Control Systems), Git tiene la posibilidad de etiquetar puntos específicos del historial como importantes. Esta funcionalidad se usa típicamente para marcar versiones de lanzamiento (v1.0, por ejemplo).
Para esto usaremos el siguiente comando:

```
    git tag -a <tagName> -m "message" <hashCommit>
```

Si se omite el HASH del `commit`, el tag se referencia al commit actual.

A continuación se listarán los comandos útiles para los tags:

|COMANDO                 |DESCRIPCIÓN                                     |
|:-----------------------|:-----------------------------------------------|
|`git tag`               |Listar los tags creados.                        |
|`git tag -l`            |Listar los tags creados.                        |
|`git show-ref --tags`   |Listar los tags creados y sus commits asociados.|
|`git push origin --tags`|Enviar los tags creados al repositorio remoto (Recordar hacer el git pull previamente).|
|`git tag -d <tagName>`  |Eliminar un tag del entorno local. Posteriormente se realiza el pull y luego el push para enviar los cambios.|
|`git push origin :ref/tags/<tagName>`|Eliminar tag del entorno remoto. Los tags de GitHub son releases y no se eliminan de igual manera como en el entorno local.|

Los `tags` no son cambios, sirven cuando necesitamos marcar un punto especifíco en la historia de nuestro trabajo (para los releases). De esta forma, podemos hacer un seguimiento al progreso de nuestro proyecto e identificar los cambios más fácilmente entre cada versión, incluso podemos hacer un checkout a uno de esos tags.

#### GIT STASH

|COMANDO         |DESCRIPCIÓN                                                    |
|:---------------|:--------------------------------------------------------------|
|`git stash`     |Toma los cambios sin confirmar (tanto los que están preparados como los que no los están), los guarda aparte para usarlos más adelante y, acto seguido, los deshace en el código en el que se está trabajando.|
|`git stash pop` |Puedes volver a aplicar los cambios de un stash mediante este comando. Al hacer pop del stash, se eliminan los cambios de este y se vuelven a aplicar en el código en que estás trabajando. De forma predeterminada este comando volverá a aplicar el último stash creado.|
|`git stash list`|Se puede listar los stash realizados con este comando.|
|`git stash drop`|Si decides que ya no necesitas algún stash en particular, puedes eliminarlo mediante este comando.|
|`git stash clear`|Comando para eliminar todos los stashes.|
|`git stash save "<message>"`|Comentar los stashes con una descripción|
|`git stash apply`|Aplicar los cambios en el código que se está trabajando y conservarlos en el stash.|
|`git stash show`|Visualizar un resumen de un stash.|
|`git stash show -p`|Ver todas las diferencias de un stash|
|`git stash pop stash@{n}`|Elegir que número "n" de stash se desea volver a aplicar|
|`git stash drop stash@{n}`|Eliminar un determinado número "n" de stash.|

>[!NOTE]
>_Nota: Por defecto git stash **NO** almacena los archivos no preparados (untracked o que no se hayan ejecutado con **git add**) y los archivos ignorados._

Si se necesita guardar en el stash estos archivos, ejecutar los siguientes comandos:

|COMANDO                        |DESCRIPCIÓN                               |
|:------------------------------|:-----------------------------------------|
|`git stash -u`                 |El stash considera los Untracked files    |
|`git stash -a`                 |El stash considera los archivos ignorados.|
|`git stash save -u "<message>"`|Considera los Untraeked y se agrega un comentario|

#### GIT CLEAN: LIMPIAR EL PROYECTO DE ARCHIVOS NO DESEADOS
Git Clean es un método adecuado para eliminar los archivos sin seguimiento en un directorio de trabajo del repositorio.

|COMANDO                        |DESCRIPCIÓN                               |
|:------------------------------|:-----------------------------------------|
|`git clean`|Si ejecutamos git clean por defecto, la consola mostrará un error **'fatal: clean.requireForce defaults to true and neither -i, -n, nor -f given; ref using to clean'**. Esto es porque por defecto y por seguridad **Git Clean** esta configurado para ser ejecutado con el parametro **-f** (force).|
|`git clean --dry-run`|Si ejecutamos `git clean --dry-run` o git clean -n , Git realizará un simulacro de borrado y se podrá ver los archivos que se van a eliminar sin que se eliminen realmente.|
|`git clean -f`|Si ejecutamos `git crean -f`, Git inicia la eliminación real de los archivos sin seguimiento del directorio actual.|
|`git clean -d`|Ya que se ignora los directorios de forma predeterminada, podemos agregar la opción **-d** a `git clean`, para indicar a Git que también se quiere eliminar los directorios sin seguimiento.|
|`git clean -x`|Indica a Git que incluya también los archivos ignorados. Al igual que ocurría con las anteriores invocaciones de git clean, se recomienda realizar un simulacro antes de la eliminación final. La opción -x actuará en los archivos ignorados.|
|`git clean -dn`|Verificar qué elementos se eliminan incluyendo ditectorios.|
|`git clean -df`|Eliminar archivos incluyendo directorios.|
|`git clean-xdf`|Eliminar archivos incluyendo los archivos ignorados y directorios.|
|`git clean -q`|Muestra en pantalla solo los mensajes de errores, no imprime los nombres de los archivos eliminados.|
|`git clean -xf`|Eliminar solo los archivos ignorados incluidos en **.gitignore**|
|`git clean -i`|Ejecuta el proceso por medio de opciones, se puede combinar con otros comandos.|

Con `git clean`, podemos eliminar archivos y/o carpetas, para tener una versión limpia de nuestro proyecto, debido a que en ocasiones tunemos elementos que han sido generados por herramientas de combinación o externas, teniendo siempre cuidado de eliminar algo por error.

#### GIT RESET Y REFLOG
Una de las cosas que Git hace en segundo plano, mientras se está trabajando a
distancia, es mantener un "`reflog`" - un log dónde se apuntan las referencias del HEAD y la rama en los últimos meses.

El reflog no forma parte del repositorio en sí (se almacena por separado) y no se incluye en los push, búsquedas o clones; es puramente local.



|COMANDOS               |DESCRIPCIÓN                                  |
|:-----------------------------|:--------------------------------------------|
|`git reflog show --all`       |Obtener un `reflog` de todas las referencias.|
|`git reflog show <branchName>`|Ver el registro de referencias de una rama concreta.|
|`git reflog stash`|Ver el registro de referencia de un stash.|

#### GIT AMEND
Este comando permite "enmendar" una confirmación, pero en realidad hace una nueva, por lo que la antigua seguirá disponible y se puede volver a ella con `git checkout`.

Comandos importantes:

|COMANDO                       |DESCRIPCIÓN                      |
|:-----------------------------|:--------------------------------|
|`git commit --amend`          |Modificar el commit más reciente.|
|`git commit --amend -m`       |Modificar el commit más reciente y su mensaje en la misma línea.|
|`git commit --amend --no-edit`|Modificar el commit sin modificar el mensaje de dicho commit.|

#### GIT GREP Y GIT LOG
Con estos dos comandos se puede buscar texto de los archivos y los commits.

* #### GIT GREP
    |COMANDO                  |DESCRIPCIÓN                                     |
    |:------------------------|:-----------------------------------------------|
    |`git grep "<keyWord>"`   |Buscar a través de cualquier árbol o directorio de trabajo con commit por una cadena de texto.|
    |`git grep -n "<keyWord>"`|Muestra los números de línea donde Git ha encontrado coincidencias.|
    |`git grep -c "<keyWord>"` o `git grep --count "<keyWord>"`|Muestra los archivos coincidentes con la palabra clave y cuántas coincidencias hay en cada uno.|
    |`git grep --untracked "<keyWord>"`|Buscar la palabra clave en los archivos incluyendo los untracked (sin seguimiento).|
    |`git grep -i "<keyWord>"`|Buscar la palabra clave en los archivos ignorando las diferencias entre mayúsculas y minúsculas.|
    |`git grep -w "<keyWord>"`|Buscar la palabra clave en los archivos considerando la palabra exacta y obviando coincidencias.|
    |`git grep -v "<keyWord>"`|Muestra solo las líneas que no coinciden o no contengan la palabra clave.|
    |`git grep -l "<keyWord>"`|Lista los archivos que contienen La palabra clave.|
    |`git grep -o "<keyWord>"`|Lista todas las coincidencias sin mostrar el detalle del archivo.|

* #### GIT LOG
    |COMANDO                  |DESCRIPCIÓN                                     |
    |:------------------------|:-----------------------------------------------|
    |`git log -S "<keyWord>"` |Muestra los commit que contiene la palabra clave tanto en los mensajeas de los commits como en el contenido de los cambios, Podemos hacer git show a los HASH del resultado para corroborar la búsqueda.|
    |`git log --grep "<keyWord>"`|Muestra los commit que contiene la expresión palabra clave solo en los mensajes de cada confirmación de los commits.|
    |`git log --oneline --grep "<keyWord>"`|Adicionar `--grep` al `git log`, permite buscar la palabra clave en los mensajes de cada commit y muestra las confirmaciones que la contengan.|

#### COMANDOS Y RECURSOS COLABORATIVOS EN GIT Y GITHUB
A continuación veremos una lista de comandos colaborativos para facilitar el trabajo remoto en GitHub:

* #### GIT SHORTLOG

    |COMANDO          |DESCRIPCIÓN|
    |:----------------|:----------|
    |`git shortlog`   |Agrupa cada confirmación por autor y muestra la primera línea de cada mensaje de confirmación. Es una forma fácil de ver quién ha estado trabajando en qué.|
    |`git shortlog -n`|Ordena la salida según el número de confirmaciones por autor en lugar de hacerlo por orden alfabético.|
    |`git shortlog -s`|Proporciona Sólo un resumen del recuento de la confirmación.|
    |`git shortlog -e`|Muestra la dirección de correo electrónico de cada autor.|
    |`git shortlog --all --merges`|Muestra solo las confirmaciones de fusión o merge.|
    |`git shortlog --all --no-merges`|Muestra todas las confirmaciones y excluye las que son por merge o fusión.|

* #### GIT ALIAS
    Si no quieres teclear el nombre completo de cada comando de Git, puedes establecer fácilmente un alias para cada comando mediante **git config**.

    ```
        git config --global alias.<nameAlias> '<command>'
    ```

* #### GIT BLAME
    El funcionamiento de `git blame` es la visualización de metadatos de autor adjuntos a líneas específicas confirmadas en un archivo. Esto se usa para examinar puntos específicos del historial de un archivo y poner en contexto quién fue el Último autor que modificó la línea.

    |COMANDO               |DESCRIPCIÓN|
    |:---------------------|:----------|
    |`git blame "<fileName>"`|Muestra los datos del archivo y quien hizo modificaciones.|
    |`git blame "<fileName>" L<startingLine>,<endingLine>`|Muestra los datos del archivo y quien hizo modificaciones de las lineas especificas del comando.|
    |`git blame -e "<fileName>"`|Muestra la dirección del email de los autores en lugar de su nombre de usuario.|
    |`git blame -c "<fileName>"`|Funciona como el comando `git blame` pero identa cada línea del archivo para mostrarlo más ordenado.|
    |`git blame -M "<fileName>"`|Detecta las líneas que se han movido o copiado dentro del mismo archivo. Esto indicará el autor original de las líneas en lugar de indicar el último autor que las ha movido o copiado.|