
![[Uso del terminal - Git bash.pdf]]
- URL Para instalar Git (https://git-scm.com/)
 - Documentación  de Git (https://git-scm.com/doc) 
 - Para comprobar versión de Git copiar y pegar este comando en la terminal
 - `git --version`

## Configurar Git con GitHub

###### - Para poder subir nuestros proyectos a GitHub, es necesario tener cuenta creada en (https://github.com/) 
#### Una vez tengamos cuenta tenemos que tener instalado Git

ingresar a Git Bash y ingresar el siguiente comando `git config`
para establecer tu nombre de usuario y correo electrónico, que son importantes para las confirmaciones.

**Configuración del Nombre de Usuario y Correo Electrónico**
`git config --global user.name "Tu Nombre"`

**Establece tu dirección de correo electrónico**
`git config --global user.email "tuemail@example.com"`

## Como enlazamos el repositorio de GitHub al proyecto de VSC?

![[Captura de pantalla 2024-12-02 184108 1.png]]
 
 Copiamos y pegamos el `...or create a new repository on the command line`
en la Terminal de VSC y quedara perfectamente enlazado, ya podremos trabajar en el

![[Captura de pantalla 2024-12-02 185046.png]]

 ##  Como Clonar un repositorio
 
 por ejemplo `git clone https://github.com/usuario/nombre-del-repositorio.git` (importante hacerlo en VSC)
 ### Abrir el repositorio en VS Code
## Si no lo abriste automáticamente, puedes abrir el repositorio en VS Code:

- Ve a `Archivo > Abrir carpeta...` y selecciona la carpeta del repositorio que acabas de clonar.
## Extensiones Git

GitLens (Se instala desde Visual Studio Code) link: (https://marketplace.visualstudio.com/items?itemName=eamodio.gitlens)
## Comandos Git 

-  `git add .`
- `git commit -m "tu mensaje"` 
- `git push` (subir cambios a tu repositorio)
- `git pull` (Traer cambios nuevos)
- `git merge origin/NombreDeLaRama` se utiliza para combinar cambios de una rama remota específica en la rama actual de tu repositorio local. Aquí, `origin` es el nombre por defecto del remoto que hace referencia al repositorio de origen (generalmente el repositorio en el que se clonó tu proyecto), y `nombredelarama` es el nombre de la rama en el repositorio remoto que deseas fusionar.
- `git merge NombreDeLaRama`  Se utiliza en Git para combinar dos ramas diferentes en una sola. Este comando permite integrar los cambios de una rama (la rama de origen) en otra (la rama de destino). Es una parte fundamental del flujo de trabajo en Git, especialmente cuando se trabaja en equipo o en proyectos que implican múltiples características o correcciones de errores.
-  `git init` Se utiliza para crear un nuevo repositorio Git vacío en el directorio actual. Al ejecutarlo, se genera un subdirectorio llamado `.git`, que contiene todos los archivos y estructuras necesarias para el control de versiones, como objetos y referencias. Este comando se usa una sola vez durante la configuración inicial de un repositorio nuevo.
-  `git status` Se utiliza en Git para mostrar el estado actual del repositorio. Proporciona información sobre los cambios en el área de trabajo y el área de preparación (staging area), así como el estado de la rama en la que te encuentras. Es una herramienta muy útil para entender qué archivos han sido modificados, cuáles están listos para ser confirmados (committed) y cuáles no están siendo rastreados por Git.
- GitHub de conventional commits (https://github.com/pvdlg/conventional-commit-types)
-  Seguid al pie de la letra los conventional commits, las empresas lo valoran mucho, especificar siempre el motivo de tu commit.

# Libros de Git + GitHub

![[Git + Github Desde Cero.pdf]]

![[git-y-github-desde-cero-2da-ed-brais-moure_compress.pdf]]