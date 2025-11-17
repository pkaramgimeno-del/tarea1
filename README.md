#  Guía de Creación y Gestión de un Repositorio con Git y GitHub

Este documento describe paso a paso cómo crear un repositorio, trabajar con ramas y subir cambios a GitHub utilizando Git desde la terminal.

---

##  1. Inicialización del Proyecto

1. Accedemos a la carpeta donde queremos crear el proyecto e inicializamos el repositorio:
   ```bash
   git init
   ```

2. Creamos el repositorio en GitHub (sin añadir *README* ni *.gitignore*).

3. Copiamos la URL del repositorio remoto (preferiblemente SSH si ya está configurado).

4. Registramos el repositorio remoto:
   ```bash
   git remote add origin <url>
   ```
   **Explicación breve:**
   - `remote`: gestiona repositorios externos  
   - `add`: añade una nueva conexión  
   - `origin`: alias por defecto para el repositorio remoto  
   - `<url>`: dirección del repositorio en GitHub  

5. Verificamos la conexión remota:
   ```bash
   git remote -v
   ```

---

##  2. Estructura Básica del Proyecto

1. Creamos el archivo principal:
   ```bash
   touch index.html
   nano index.html
   ```
   Agregamos contenido HTML básico.

2. Creamos un archivo `.gitignore` con los archivos o carpetas que queremos excluir del control de versiones.

---

##  3. Primer Commit y Push

1. Revisamos el estado del repositorio:
   ```bash
   git status
   ```

2. Añadimos los archivos al *staging area*:
   ```bash
   git add .
   ```

3. Creamos el primer commit:
   ```bash
   git commit -m "primer commit"
   ```

4. Renombramos la rama principal a `main`:
   ```bash
   git branch -M main
   ```

5. Subimos el trabajo al repositorio remoto:
   ```bash
   git push origin main
   ```

---

## 4. Trabajo por Ramas (Mejoras del Proyecto)

1. Creamos dos ramas de trabajo:
   ```bash
   git branch feature/modificacion1
   git branch feature/modificacion2
   ```

2. Entramos en la primera rama:
   ```bash
   git checkout feature/modificacion1
   ```
   Aquí añadimos una **tabla de horarios**.

3. Guardamos cambios:
   ```bash
   git add .
   git commit -m "primera modificación"
   git push origin feature/modificacion1
   ```

4. Repetimos lo mismo para la segunda rama, donde añadimos un **footer con redes sociales**.

---

## 5. Integración de las Ramas en `main`

1. Volvemos a `main`:
   ```bash
   git checkout main
   ```

2. Fusionamos las dos ramas:
   ```bash
   git merge feature/modificacion1
   git merge feature/modificacion2
   ```

3. Obtenemos los últimos cambios del repositorio remoto:
   ```bash
   git pull origin main
   ```

4. Si Git genera comentarios durante la fusión, los eliminamos y subimos nuevamente:
   ```bash
   git add .
   git commit -m "quitamos comentarios git"
   git push origin main
   ```

---
