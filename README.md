# Practica Curso Git y Github Platzi
[![](https://lh3.googleusercontent.com/jtzTjhtikH8etHX8DX_p3Ah7cPrMbBQKLgBpylWt6EjaZU_Z2bm5T1M87O3pQhRnkHt68hCq9MSOjc0A1rwZbPdlUsaecc8yRnBYXA=h600)](https://lh3.googleusercontent.com/jtzTjhtikH8etHX8DX_p3Ah7cPrMbBQKLgBpylWt6EjaZU_Z2bm5T1M87O3pQhRnkHt68hCq9MSOjc0A1rwZbPdlUsaecc8yRnBYXA=h600)


Curso de Git - Platzi 

## Configuración Básica

Configurar Nombre que salen en los commits

```
	git config --global user.name "dasdo"

```

Configurar Email

```
	git config --global user.email dasdo1@gmail.com

```

Marco de colores para los comando

```
	git config --global color.ui true

```

## Iniciando repositorio

Iniciamos GIT en la carpeta donde esta el proyecto

```
	git init

```

Clonamos el repositorio de github o bitbucket

```
	git clone <url>

```

Añadimos todos los archivos para el commit

```
	git add .

```

Hacemos el primer commit

```
	git commit -m "Texto que identifique por que se hizo el commit"

```

subimos al repositorio

```
	git push origin master

```

## GIT CLONE

Clonamos el repositorio de github o bitbucket

```
	git clone <url>

```

Clonamos el repositorio de github o bitbucket ?????

```
	git clone <url> git-demo

```

## GIT ADD

Añadimos todos los armchivos para el commit

```
	git add .

```

Añadimos el archivo para el commit

```
	git add <archivo>

```

Añadimos todos los archivos para el commit omitiendo los nuevos

```
	git add --all

```

Añadimos todos los archivos con la extensión especificada

```
	git add *.txt

```

Añadimos todos los archivos dentro de un directorio y de una extensión especifica

```
	git add docs/*.txt

```

Añadimos todos los archivos dentro de un directorios

```
	git add docs/

```

## GIT COMMIT

Cargar en el HEAD los cambios realizados

```
	git commit -m "Texto que identifique por que se hizo el commit"

```

Agregar y Cargar en el HEAD los cambios realizados

```
	git commit -a -m "Texto que identifique por que se hizo el commit"

```

De haber conflictos los muestra

```
	git commit -a

```

Agregar al ultimo commit, este no se muestra como un nuevo commit en los logs. Se puede especificar un nuevo mensaje

```
	git commit --amend -m "Texto que identifique por que se hizo el commit"

```

## GIT RESET

Nos permite volver a una versión anterior. Existen 2 opciones de git reset el duro y el suave:

- git reset --hard (Devuelve todo a la última versión)
- git reset --soft ( Volvemos a la versión anterior pero todo lo que tenemos en staging sigue hay. Quiere decir que todo lo que se haya enviado al staging con git add . sigue hay

```
//Git Reset Duro
git reset 7d821e2d551bfea8dc69dbc2e45b8aae0ab603d5 --hard 

//Git Reset Suave
git reset 7d821e2d551bfea8dc69dbc2e45b8aae0ab603d5 --soft 

```

Para ver las diferencias entre el directorio de trabajo, en staging y en mi repositorio actual se usa git diff

```
git diff
```

Para ver a que archivos se le realizaron cambios podemos comprobarlo con git log —stat

```
git log --stat
```

Con git commit -am automaticamente hace el commit de los cambios pero solo funciona con los archivos que se le han realizado un add previamente

```
git commit -am
```

## GIT PUSH

Subimos al repositorio

```
	git push <origien> <branch>

```

Subimos un tag

```
	git push --tags

```

## GIT LOG

Muestra los logs de los commits

```
	git log

```

Muestras los cambios en los commits

```
	git log --oneline --stat

```

Muestra graficos de los commits

```
	git log --oneline --graph

```

## GIT DIFF

Muestra los cambios realizados a un archivo

```
	git diff
	git diff --staged

```

## GIT HEAD

Saca un archivo del commit

```
	git reset HEAD <archivo>

```

Devuelve el ultimo commit que se hizo y pone los cambios en staging

```
	git reset --soft HEAD^

```

Devuelve el ultimo commit y todos los cambios

```
	git reset --hard HEAD^

```

Devuelve los 2 ultimo commit y todos los cambios

```
	git reset --hard HEAD^^

```

Rollback merge/commit

```
	git log
	git reset --hard <commit_sha>

```

## GIT REMOTE

Agregar repositorio remoto

```
	git remote add origin <url>

```

Cambiar de remote

```
	git remote set-url origin <url>

```

Remover repositorio

```
	git remote rm <name/origin>

```

Muestra lista repositorios

```
	git remote -v

```

Muestra los branches remotos

```
	git remote show origin

```

Limpiar todos los branches eliminados

```
	git remote prune origin

```

## GIT BRANCH - CREANDO RAMAS EN GIT

Crea un branch

```
	git branch <nameBranch>

```

Moverme a la cabecera creada con git cheackout + (nombre de la rama  creada)

```
	git checkout "cabecera"

```

Lista los branches identifica cuantas ramas hay y en cual estoy actualmente

```
	git branch

```

Comando -d elimina el branch y lo une al master

```
	git branch -d <nameBranch>

```

Elimina sin preguntar

```
	git branch -D <nameBranch>

```

## GIT TAG

Muestra una lista de todos los tags

```
	git tag

```

Crea un nuevo tags

```
	git tag -a <verison> - m "esta es la versión x"

```

## GIT REBASE

Los rebase se usan cuando trabajamos con branches esto hace que los branches se pongan al día con el master sin afectar al mismo

Une el branch actual con el mastar, esto no se puede ver como un merge

```
	git rebase

```

Cuando se produce un conflicto no das las siguientes opciones:

cuando resolvemos los conflictos --continue continua la secuencia del rebase donde se pauso

```
	git rebase --continue

```

Omite el conflicto y sigue su camino

```
	git rebase --skip

```

Devuelve todo al principio del rebase

```
	git reabse --abort

```

Para hacer un rebase a un branch en especifico

```
	git rebase <nameBranch>

```

## OTROS COMANDOS

Lista un estado actual del repositorio con lista de archivos modificados o agregados

```
	git status

```

Quita del HEAD un archivo y le pone el estado de no trabajado

```
	git checkout -- <file>

```

Crea un branch en base a uno online

```
	git checkout -b newlocalbranchname origin/branch-name

```

Busca los cambios nuevos y actualiza el repositorio

```
	git pull origin <nameBranch>

```

Cambiar de branch

```
	git checkout <nameBranch/tagname>

```

Une el branch actual con el especificado

```
	git merge <nameBranch>

```

Verifica cambios en el repositorio online con el local

```
	git fetch

```

Borrar un archivo del repositorio

```
	git rm <archivo>

```

## Fork

Descargar remote de un fork

```
	git remote add upstream <url>

```

Merge con master de un fork

```
	git fetch upstream
	git merge upstream/master
```



Git reset y git rm son comandos con utilidades muy diferentes, pero se pueden confundir muy fácilmente.

## git rm

Este comando nos ayuda a eliminar archivos de Git sin eliminar su historial del sistema de versiones. Esto quiere decir que si necesitamos recuperar el archivo solo debemos “viajar en el tiempo” y recuperar el último commit antes de borrar el archivo en cuestión.

Recuerda que `git rm` no puede usarse así nomás. Debemos usar uno de los flags para indicarle a Git cómo eliminar los archivos que ya no necesitamos en la última versión del proyecto:

- `git rm --cached`: Elimina los archivos de nuestro repositorio local y del área de staging, pero los mantiene en nuestro disco duro. Básicamente le dice a Git que deje de trackear el historial de cambios de estos archivos, por lo que pasaran a un estado `untracked`.
- `git rm --force`: Elimina los archivos de Git y del disco duro. Git siempre guarda todo, por lo que podemos acceder al registro de la existencia de los archivos, de modo que podremos recuperarlos si es necesario (pero debemos usar comandos más avanzados).

## git reset

Este comando nos ayuda a volver en el tiempo. Pero no como `git checkout` que nos deja ir, mirar, pasear y volver. Con `git reset` volvemos al pasado sin la posibilidad de volver al futuro. Borramos la historia y la debemos sobreescribir. No hay vuelta atrás.

Este comando es **muy peligroso** y debemos emplearlo solo en caso de emergencia. Recuerda que debemos usar alguna de estas dos opciones:

Hay dos formas de utilizar `git reset`: con el argumento `--hard`, borrando toda la información que tengamos en el área de staging (y perdiendo todo para siempre). O, un poco más seguro, con el argumento `--soft`, que mantiene allí los archivos del área de staging para que podamos aplicar nuestros últimos cambios pero desde un commit anterior.

- `git reset --soft`: Borramos todo el historial y los registros de Git pero guardamos los cambios que tengamos en Staging, así podemos aplicar las últimas actualizaciones a un nuevo commit.
- `git reset --hard`: Borra todo. Todo todito, absolutamente todo. Toda la información de los commits y del área de staging se borra del historial.

**¡Pero todavía falta algo!**

- `git reset HEAD`: Este es el comando para sacar archivos del área de staging. No para borrarlos ni nada de eso, solo para que los últimos cambios de estos archivos no se envíen al último commit, a menos que cambiemos de opinión y los incluyamos de nuevo en staging con `git add`, por supuesto.

## La relevancia de estos comandos

Imagina el siguiente caso:

Hacemos cambios en los archivos de un proyecto para una nueva actualización. Todos los archivos con cambios se mueven al área de staging con el comando `git add`. Pero te das cuenta de que uno de esos archivos no está listo todavía. Actualizaste el archivo, pero ese cambio no debe ir en el próximo commit por ahora.

¿Qué podemos hacer?

Bueno, todos los cambios están en el área de Staging, incluido el archivo con los cambios que no están listos. Esto significa que debemos sacar ese archivo de Staging para poder hacer commit de todos los demás.

¡Al usar `git rm` lo que haremos será eliminar este archivo completamente de git! Todavía tendremos el historial de cambios de este archivo, con la eliminación del archivo como su última actualización. Recuerda que en este caso no buscábamos eliminar un archivo, solo dejarlo como estaba y actualizarlo después, no en este commit.

En cambio, si usamos `git reset HEAD`, lo único que haremos será mover estos cambios de Staging a Unstaged. Seguiremos teniendo los últimos cambios del archivo, el repositorio mantendrá el archivo (no con sus últimos cambios, pero sí con los últimos en los que hicimos commit) y no habremos perdido nada.

**Conclusión**: Lo mejor que puedes hacer para salvar tu puesto y evitar un incendio en tu trabajo es conocer muy bien la diferencia y los riesgos de todos los comandos de Git.
## Comandos para trabajo remoto con GIT

- **`git clone url_del_servidor_remoto`**: Nos permite descargar los archivos de la última versión de la rama principal y todo el historial de cambios en la carpeta `.git`.
- **`git push`**: Luego de hacer `git add` y `git commit` debemos ejecutar este comando para mandar los cambios al servidor remoto.
- **`git fetch`**: Lo usamos para traer actualizaciones del servidor remoto y guardarlas en nuestro repositorio local (en caso de que hayan, por supuesto).
- **`git merge`**: También usamos el comando `git merge` con servidores remotos. Lo necesitamos para combinar los últimos cambios del servidor remoto y nuestro directorio de trabajo.
- **`git pull`**: Básicamente, `git fetch` y `git merge` al mismo tiempo.

Adicionalmente, tenemos otros comandos que nos sirven para trabajar en proyectos muy grandes:

- **git log --oneline**:Te muestra el id commit y el título del commit.
- **git log --decorate**: Te muestra donde se encuentra el head point en el log.
- **git log --stat**: Explica el número de líneas que se cambiaron brevemente.
- **git log -p**: Explica el número de líneas que se cambiaron y te muestra que se cambió en el contenido.
- **git shortlog**: Indica que commits ha realizado un usuario, mostrando el usuario y el título de sus commits.
- **git log --graph --oneline --decorate** y
- **git log --pretty=format:"%cn hizo un commit %h el dia %cd"**: Muestra mensajes personalizados de los commits.
- **git log -3**: Limitamos el número de commits.
- **git log --after=“2018-1-2”**
- **git log --after=“today”** y
- **git log --after=“2018-1-2” --before=“today”**: Commits para localizar por fechas.
- **git log --author=“Name Author”**: Commits hechos por autor que cumplan exactamente con el nombre.
- **git log --grep=“INVIE”**: Busca los commits que cumplan tal cual está escrito entre las comillas.
- **git log --grep=“INVIE” –i**: Busca los commits que cumplan sin importar mayúsculas o minúsculas.
- **git log – index.html**: Busca los commits en un archivo en específico.
- **git log -S “Por contenido”**: Buscar los commits con el contenido dentro del archivo.
- **git log > log.txt**: guardar los logs en un archivo txt

Cuando empiezas a trabajar en un entorno local, el proyecto vive únicamente en tu computadora. Esto significa que no hay forma de que otros miembros del equipo trabajen en él.

Para solucionar esto, utilizamos los **servidores remotos**: un nuevo estado que deben seguir nuestros archivos para conectarse y trabajar con equipos de cualquier parte del mundo.

Estos servidores remotos pueden estar alojados en GitHub, GitLab, BitBucket, entre otros. Lo que van a hacer es guardar el mismo repositorio que tienes en tu computadora y darnos una URL con la que todos podremos acceder a los archivos del proyecto. Así, el equipo podrá descargarlos, hacer cambios y volverlos a enviar al servidor remoto para que otras personas vean los cambios, comparen sus versiones y creen nuevas propuestas para el proyecto.

Esto significa que debes aprender algunos nuevos comandos

## Comandos para trabajo remoto con GIT

- **`git clone url_del_servidor_remoto`**: Nos permite descargar los archivos de la última versión de la rama principal y todo el historial de cambios en la carpeta `.git`.
- **`git push`**: Luego de hacer `git add` y `git commit` debemos ejecutar este comando para mandar los cambios al servidor remoto.
- **`git fetch`**: Lo usamos para traer actualizaciones del servidor remoto y guardarlas en nuestro repositorio local (en caso de que hayan, por supuesto).
- **`git merge`**: También usamos el comando `git merge` con servidores remotos. Lo necesitamos para combinar los últimos cambios del servidor remoto y nuestro directorio de trabajo.
- **`git pull`**: Básicamente, `git fetch` y `git merge` al mismo tiempo.

Adicionalmente, tenemos otros comandos que nos sirven para trabajar en proyectos muy grandes:

- **git log --oneline**:Te muestra el id commit y el título del commit.
- **git log --decorate**: Te muestra donde se encuentra el head point en el log.
- **git log --stat**: Explica el número de líneas que se cambiaron brevemente.
- **git log -p**: Explica el número de líneas que se cambiaron y te muestra que se cambió en el contenido.
- **git shortlog**: Indica que commits ha realizado un usuario, mostrando el usuario y el título de sus commits.
- **git log --graph --oneline --decorate** y
- **git log --pretty=format:"%cn hizo un commit %h el dia %cd"**: Muestra mensajes personalizados de los commits.
- **git log -3**: Limitamos el número de commits.
- **git log --after=“2018-1-2”**
- **git log --after=“today”** y
- **git log --after=“2018-1-2” --before=“today”**: Commits para localizar por fechas.
- **git log --author=“Name Author”**: Commits hechos por autor que cumplan exactamente con el nombre.
- **git log --grep=“INVIE”**: Busca los commits que cumplan tal cual está escrito entre las comillas.
- **git log --grep=“INVIE” –i**: Busca los commits que cumplan sin importar mayúsculas o minúsculas.
- **git log – index.html**: Busca los commits en un archivo en específico.
- **git log -S “Por contenido”**: Buscar los commits con el contenido dentro del archivo.
- **git log > log.txt**: guardar los logs en un archivo txt