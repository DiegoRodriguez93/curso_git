# Curso de git

### Elace de descarga

[WINDOWS](http://git-scm.com/download/win)

### Luego reiniciar comprobar que git este instalado correctamente
```
git --version
```
Deberiamos obtener algo como "git version 2.31.1"

### Ahora debemos configurar git por unica vez con email y nombre
```
git config --global user.name "Diego Rodriguez"
git config --global user.email  "drodriguez@ibec.edu.uy"
``` 

Ahora tenemos que ingresar a la carpeta donde vamos a trabajar con git yo cree una carpeta en mi escritorio, si inician a powershell desde el inicio o con la tecla windows + r pueden
usar 
```
cd Desktop
```
```
mkdir curso_git
```
```
cd curso_git
```
O tambien podrian crear una carpeta donde quieran y con shift + 
boton derecho les va a aparecer abrir ventana de powershell aqui
o con boton derecho sobre la carpeta que quieran trabar van a ver un acceso directo a abrir con git bash.

![Git Bash](https://i.imgur.com/SRJ924C.png)

### Para iniciar git en una carpeta
```
git init
```
### Para comprobar si git esta iniciado con ls -a puedo ver si se creo la carpeta .git
```
ls -a
```
### En esta instancia yo cree dos archivos usando el comando, pero sino pueden crearlo de la manera que ustedes quieran
```
echo "" > README.md
```
```
echo "" > index.html
```

### Para agregar el archivo al estado de trabajo, el comando es git add + el nombre del archivo EJ
```
git add README.md
```
### Para agregar todo los archivos
```
git add .
```
### Para ver el estado 
```
git status
```
### Para agregar los commit
```
git commit -m "el mensaje para guardar"
```
### Para ver todos los commit
```
git log
```
### Para ver todos los branch
```
git branch
```
### Para crear el branch
```
git checkout -b "nombre_de_branch"
```
### Para cambiar de branch git checkout + nombre del branch
```
git checkout nombre_de_branch
```
### Para renombrar archivos en nuestra carpeta actualizando el stage de trabajo a la vez
```
git mv index.html index2.html
```
### Para traer cambios de otro branch estar parado en el branch al que se le van a cargar los cambios
```
git merge nombre_de_branch
```
### Para pararnos en un commit anterior git checkout + hash del commit o los primero 4 digitos EJ,( para ver los hash - git log )
```
git checkout c399d0ba75752e58e35b5dba108bf5fb0b0aaee1
git checkout c399
```
### Para crear branch en esa instancia (estando parado en el commit)
```
git switch -c "nombre_de_nuevo_brach"
```
### Podemos comparar dos commit con sus hashs,( para ver los hash - git log )
```
git diff c399d0ba75752e58e35b5dba108bf5fb0b0aaee1 696e4c6d3ce8ec2e18a5a08c2df4a63629f4cb3e 
```
## Segunda clase

### Como clonar un repositorio, git clone url_del_repo nombre_de_la_carpeta(opcional)
```
git clone https://github.com/diegorodriguez93/curso_git 
```
### Creando un nuevo repo y subiendo a la github a traves de la consola paso a paso
```
mkdir mi_primer_repo_de_git
cd mi_primer_repo_de_git
echo "# Mi Primer repositorio en github" > README.md
git init
git add .
git commit -m "mi primer commit"
git branch -M "main"
git remote add origin mi_primer_repo_de_git 
git push origin main
```
### Para crear un nuevo branch y subirlo a github, estando en nuestro repositorio
```
git checkout -b "nombre_del_nuevo_branch"
git push origin nombre_del_nuevo_branch
```
### para ignorar archivos de git, debemos agregar un archivo con el nombre .gitignore en la raiz del proyecto la estructura para ignorar archivos es la siguiente
```
# mi archivo de log
mi.log

# nueva carpeta
nueva_carpeta/

# otra carpeta crear una regla
otra_carpeta/
!otra_carpeta/archivo_no_ignorado

# ignorar todos los archivos con cierta extension
*.log

# ignorar archivos de config
.DS_Store
```
