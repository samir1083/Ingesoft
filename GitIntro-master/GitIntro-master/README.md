# "Copialina"
## Configurar los datos del usuario
- `git config --global user.name "Diego Guevara"`
- `git config --global user.email d_guevara@javeriana.edu.co`
## Para verificar los cambios:
- `git config --list`
## Ayuda, listar commandos
- `git`
- `git help verb`
## Para crear un repositorio se tienen dos opciones:
Tomar un directorio existente que no tenga control de versiones y convertirlo.
- Clonar un repositorio existente de algún sitio.
- Ubicarse en el directorio e invocar `git init`
- `cd FIS/2230/` -> para entrar en una carpeta
- `mkdir GitIntro` -> para crear una carpeta
- `cd GitIntro` -> para entrar en una carpeta
- `git init`
```
Initialized empty Git repository in C:\Users\Diego Guevara\Documents\FIS\2230\GitIntro
```
## Comandos básicos:
- `git status`
```
On branch master
Initial commit
nothing to commit (create/copy files and use "git add" to track)
```
### Si se agrega un archivo al directorio:
- `git status`
```
On branch master
Initial commit
Untracked files: (use "git add<file>..." to include in what will be committed)
Ejemplo1.txt
nothing added to commit but untracked files present (use "git add" to track)
```
## Agrega el archivo de untracked al staged area
- `git add Ejemplo1.txt`
- `git status`
```
On branch master
Initial commit
Changes to be committed:
(use "git rm --cached<file>..." to unstage)
    new file: Ejemplo1.txt
```
-  `git add .` -> Agrega todos los archivos
## Crear un archivo de texto con nombre LICENSE con el siguiente contenido:
```
LICENSE
    This is a LICENSE file of Diego Guevara
```
- `git add LICENSE`
- Modificar el archivo LICENSE.txt después de haber sido agregado al repositorio
```
LICENSE
    This is a modified LICENSE file of Diego Guevara
```
### Si se modifica un archivo, la versión que queda en el staging area lista para el commit es la que se tenía en el momento del add.
- `git status`
```
On branch master
Initial commit
Changes to be committed: (use "git rm --cached<file>..." to unstage)
    new file: LICENSE
    new file: Ejemplo1.txt
Changes not staged for commit: 
(use "git add<file>..." to update what will be committed)
(use "git checkout --<file>..." to discard changes in working directory)
    modified: LICENSE
```
- `git add LICENSE`

## Guarda los cambios listos desde el staging area en el repositorio:
- `git commit` -> Lanza automáticamente el editor de texto por defecto para que se ingrese el mensaje del commit
- `git commit –m "Mensaje del commit"` -> Se ingresa el mensaje directamente desde el comando
- `git commit –a –m "Mensaje del commit"`-> Se usa si se quiere saltar el paso de “git add”, se agrega todo lo que este modificado como parte del commit **Not Recommended**

## Otros comandos
- Permite consultar todos los archivos que están guardados en esa ubicación en el repositorio: `git ls-files`
- Muestran la historia de todos los commits que se han hecho: `git log`
- Revierte la modificación sobre algún archivo antes del commit: `git checkout -- <file>`
- Muestra las diferencias entre el archivo del snapshot y el archivo del Stage (modified): `git diff archivo`

## Comandos para el manejo de ramas:
- Muestra las ramas actuales: `git branch`
- Crea la rama con el nombre dado `git branch <nombre_rama>`
- Selecciona la rama con la que se quiere trabajar: `git checkout <nombre_rama>`
- Actualiza la rama actual en la que se está trabajando, con la información de la rama que se pasa como parámetro. Si el merge tiene problemas, se deben resolver los conflictos de forma manual como en cualquier sistema CVS: `git merge <nombre_rama>`
- Borra la rama: `git branch –d <nombre_rama>`

## Para borrar un archivo se utiliza el commando git rm:
- La próxima vez que se haga commit, el archivo desaparece: `git rm LICENSE`
- El archivo se borra del repositorio pero sigue existiendo en la carpeta de trabajo: `git rm --cached LICENSE`

## Para subir código a un repo en Github (suponiendo que el repositorio remoto ya está creado)
- `git remote add origin https://github.com/FIS-2230/GitIntro.git`
- Subir los cambios de master (pide los datos de autenticación con github): `git push -u origin master`
- Sube los cambios de la rama: `git push origin <rama>`
- Borra la rama del repositorio remoto: `git push --delete <rama>`
- el commando git branch –d <rama> solo lo borra del repo local

## Para clonar un repo en Github (suponiendo que el repositorio remoto ya está creado)
Un repositorio se puede clonar desde una ubicación remota, como GitHub o BitBucket:
- `git clone https://github.com/FIS-2230/GitIntro.git`
- En caso de querer cambiar de nombre el directorio destino: `git clone https://github.com/FIS-2230/GitIntro.git <nombre_nuevo>`

# Ejercicio
1. Instale Git en su máquina.
2. Configure las variables de nombre y correo del usuario globalmente.
3. Cree un repositorio local que se llame my_localrepo
4. Utilizando un editor de texto de su preferencia, defina dos archivos, un archivo de texto LICENSE.txt y un archivo de texto Ejemplo1.txt que diga su nombre y la fecha actual
5. Verifique el estado del repositorio (git status)
6. Agregue los archivos al área de stage del repositorio
7. Verifique el estado del repositorio (git status)
8. Haga commit de los datos a su repositorio local
9. Verifique el estado del repositorio (git status)
10. Modifique el archivo readme agregando una nueva fecha
11. Agregue el archivo al stage y haga commit
12. Cree una rama llamada date
13. Cree un archivo date.txt dentro de la rama
14. Haga merge de la rama con master y borre la rama

# **¡Quiz!**
**Importante: haga un commit por cada cambio o adición**
1. Clone el repositorio https://github.com/FIS-2230/GitIntro.git
2. Cree una branch con su nombre i.e. diego_guevara
3. Agregue el archivo MyBio.txt y como contenido ponga su nombre, semestre y 3 hobbies
4. Modifique el archivo LICENSE y ponga su nombre
5. Agregue un meme de su elección (jpg o png) **¡NADA MUY EXPLÍCITO POR FAVOR!**
6. Suba los commits al repositorio remoto
