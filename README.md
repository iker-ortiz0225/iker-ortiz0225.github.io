# Ejecución del sitio (MkDocs + GitHub Pages)

Guía para que cualquier persona pueda **clonar**, **ejecutar en local** y **desplegar** este sitio sin repetir el proceso de creación.

## Requisitos
- Linux (o WSL/VM con Linux)
- Git y Python 3.7+ (con `pip`)
- Navegador web

## 1. Clonar el repositorio
```bash
git clone https://github.com/iker-ortiz0225/iker-ortiz0225.github.io.git

cd iker-ortiz0225.github.io
```

## 2. Entorno e instalación
Opción recomendada con entorno virtual:

```bash
python3 -m venv venv
source venv/bin/activate
pip install -r requirements.txt
```

O bien (si prefieres instalar lo mínimo necesario):
```bash
pip install mkdocs mkdocs-dracula-theme
```

## 3. Ejecutar en local

Ejecutar desde la raíz del repositorio (donde está mkdocs.yml).
```bash
mkdocs serve
```
Abrir en el navegador la URL que muestre el comando (normalmente http://127.0.0.1:8000/).
Detener con Ctrl+C.


## 4. Desplegar en GitHub Pages

Publica el sitio en la rama gh-pages.
```bash
mkdocs gh-deploy
```
Si es la primera vez o hay problemas de visualización, comprobar en GitHub:

Settings → Pages → Source: Deploy from a branch
Branch: gh-pages / Folder: /


## 5. Actualizar contenido

Después de modificar docs/* o mkdocs.yml:

```bash
# (opcional) probar en local
mkdocs serve

# desplegar cambios
mkdocs gh-deploy
```


## 6. Estructura del proyecto
```bash
.
├─ docs/            # contenido en Markdown
│  ├─ index.md
│  ├─ sobre-mi.md
│  ├─ proyectos.md
│  └─ contacto.md
├─ mkdocs.yml       # configuración del sitio (tema, nav, site_url, etc.)
├─ requirements.txt # dependencias (mkdocs, tema, etc.)
└─ venv/            # (opcional) entorno virtual local
```

## 7. Notas

Lanza mkdocs serve o mkdocs gh-deploy siempre desde la carpeta donde está mkdocs.yml.


site_url en mkdocs.yml debe ser una URL válida, por ejemplo:
```bash
site_url: https://iker-ortiz0225.github.io iker-ortiz0225.github.io/
```
Para cambiar el tema, en mkdocs.yml:
```bash
theme:
  name: dracula
```


