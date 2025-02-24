


---

## Uso del Terminal - Git Bash

- **URL para instalar Git**: [Git SCM](https://git-scm.com/)
- **Documentación de Git**: [Documentación Git](https://git-scm.com/doc)
- **Comprobar versión de Git**: Ejecuta el siguiente comando en la terminal:
  ```bash
  git --version
  ```

---

## Configurar Git con GitHub

Para poder subir nuestros proyectos a GitHub, es necesario tener una cuenta creada en [GitHub](https://github.com/). Una vez que tengas la cuenta, asegúrate de tener instalado Git.

1. Abre Git Bash y ejecuta el siguiente comando para establecer tu nombre de usuario y correo electrónico, que son importantes para las confirmaciones:
   ```bash
   git config --global user.name "Tu Nombre"
   ```
   ```bash
   git config --global user.email "tuemail@example.com"
   ```

---

## Enlazar el Repositorio de GitHub al Proyecto en VS Code

Copia y pega el comando `...or create a new repository on the command line` en la terminal de VS Code para enlazar el repositorio.

---

## Clonar un Repositorio

Para clonar un repositorio, utiliza el siguiente comando (importante hacerlo en VS Code):
```bash
git clone https://github.com/usuario/nombre-del-repositorio.git
```

### Abrir el Repositorio en VS Code

Si no se abre automáticamente, ve a `Archivo > Abrir carpeta...` y selecciona la carpeta del repositorio que acabas de clonar.

---

## Comandos Git

- **Agregar cambios**:
  ```bash
  git add .
  ```

- **Confirmar cambios**:
  ```bash
  git commit -m "tu mensaje"
  ```

- **Subir cambios a tu repositorio**:
  ```bash
  git push
  ```

- **Traer cambios nuevos**:
  ```bash
  git pull
  ```

- **Combinar cambios de una rama remota**:
  ```bash
  git merge origin/NombreDeLaRama
  ```

- **Combinar dos ramas**:
  ```bash
  git merge NombreDeLaRama
  ```

- **Inicializar un nuevo repositorio**:
  ```bash
  git init
  ```

- **Mostrar el estado actual del repositorio**:
  ```bash
  git status
  ```

- **Conventional Commits**: Sigue las pautas de [Conventional Commits](https://github.com/pvdlg/conventional-commit-types) y especifica siempre el motivo de tu commit.

Esta guía proporciona una guía clara y concisa sobre el uso de Git y su configuración con GitHub