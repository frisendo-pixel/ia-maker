# Documentación del proyecto: Landing Page Personal

**Autor:** Javier de Frutos
**Fecha:** Noviembre de 2026
**Tecnología:** HTML5 + Tailwind CSS (sin backend, sin base de datos)

---

## 1. Descripción general

Landing page personal desarrollada como proyecto estático, compuesta únicamente por
**HTML, CSS (Tailwind) y JavaScript mínimo** para el menú móvil. No tiene backend ni
base de datos: el archivo `index.html` contiene toda la página y se sirve tal cual.

| Dato | Valor |
|---|---|
| Nombre del proyecto | LandingPage |
| Repositorio local | `wksOpenCode\LandingPage` |
| Archivo principal | `index.html` |
| Stack | HTML5 semántico + Tailwind CSS (vía CDN) |
| Despliegue | GitHub Pages (automático con GitHub Actions) |

---

## 2. Enlaces importantes

| Recurso | URL |
|---|---|
| **Página pública (producción)** | https://frisendo.github.io/ia-maker/ |
| **Repositorio en GitHub** | https://github.com/frisendo/ia-maker |
| WSDL/página en repo | https://github.com/frisendo/ia-maker/blob/main/index.html |
| Configuración de Pages | https://github.com/frisendo/ia-maker/settings/pages |
| Estado del despliegue | https://github.com/frisendo/ia-maker/actions |

---

## 3. Datos de Git

| Dato | Valor |
|---|---|
| Usuario de GitHub | `frisendo` |
| Email de commit | `frisendo@gmail.com` |
| Remoto (`origin`) | `https://github.com/frisendo/ia-maker.git` |
| Rama principal | `main` |
| Remoto por defecto para push/pull | `origin/main` |

**Historial de commits:**

```
1f85ae7  Primer commit: proyecto Astro LandingPage
fb48910  Cambiar a HTML + Tailwind y añadir despliegue con GitHub Pages
1ba6d1b  Personalizar contenido
```

**Comandos habituales:**

```powershell
# Clonar el repositorio en otro equipo
git clone https://github.com/frisendo/ia-maker.git

# Subir cambios
git add .
git commit -m "Descripción del cambio"
git push

# Descargar cambios
git pull
```

---

## 4. Cumplimiento de los requisitos

### ✅ La página está desplegada y accesible desde una URL pública

- Desplegada en **GitHub Pages** mediante un workflow de **GitHub Actions**
  (`.github/workflows/deploy.yml`).
- Cada `push` a la rama `main` publica automáticamente la nueva versión.
- URL pública: **https://frisendo.github.io/ia-maker/**

### ✅ La estructura HTML es semántica

El `index.html` usa etiquetas semánticas de HTML5:

| Etiqueta | Uso en la página |
|---|---|
| `<header>` | Cabecera fija con navegación |
| `<nav>` | Menú principal (escritorio y móvil), con `aria-label` |
| `<main>` | Contenedor del contenido principal |
| `<section>` | Cada una de las secciones (Inicio, Sobre mí, Habilidades, Proyectos, Contacto) con `id` anclable |
| `<article>` | Tarjetas de habilidades y de proyectos |
| `<h1>` / `<h2>` / `<h3>` | Jerarquía de títulos correcta (un solo `h1` en el hero) |
| `<footer>` | Pie de página con enlaces sociales |
| `<ul>` / `<li>` | Listas de menú y de puntos clave |
| Atributos ARIA | `aria-label`, `aria-expanded`, `aria-hidden` en botón e iconos |

### ✅ El diseño es responsive

- `<meta name="viewport" ...>` en el `<head>` para adaptación a móvil.
- **Menú hamburguesa en móvil** (`< md`) con JavaScript accesible; menú horizontal en escritorio (`md:` en adelante).
- Grids fluidos que se adaptan por breakpoints de Tailwind:
  - Habilidades: `sm:grid-cols-2 lg:grid-cols-4`
  - Proyectos: `md:grid-cols-2`
  - Hero: tipografía `text-4xl md:text-6xl`, botones apilados en móvil (`flex-col sm:flex-row`)
- Scroll suave (`scroll-smooth`) y navegación por anclas.

### ✅ Los estilos están implementados con Tailwind

- Tailwind CSS cargado por CDN: `<script src="https://cdn.tailwindcss.com"></script>`
- Configuración de tema propia en `tailwind.config` (paleta de color `primary`).
- Utilidades de Tailwind para todo el diseño (layout, tipografía, color, sombras, transiciones). No hay hoja de estilos CSS propia.

### ✅ El código está subido a un repositorio de GitHub

- Repositorio: **https://github.com/frisendo/ia-maker** (rama `main`).
- Despliegue reproducible desde el propio repositorio (infraestructura como código en `.github/workflows/deploy.yml`).

### ✅ La página incluye las secciones mínimas

| Sección | `id` | Contenido |
|---|---|---|
| Cabecera / navegación | — | Logo, menú de secciones, botón de contacto, menú móvil |
| **Inicio (Hero)** | `#inicio` | Nombre, titular, botones "Ver proyectos" y "Contactar" |
| **Sobre mí** | `#sobre-mi` | Presentación personal y puntos clave |
| **Habilidades** | `#habilidades` | 4 tarjetas: HTML & CSS, JavaScript, Git & GitHub, Inteligencia Artificial |
| **Proyectos** | `#proyectos` | Tarjetas de proyectos con enlace a GitHub |
| **Contacto** | `#contacto` | Botón de envío de correo (`mailto:`) |
| Pie de página | — | Copyright, enlaces a GitHub/LinkedIn, volver arriba |

---

## 5. Estructura del proyecto

```
LandingPage/
├── index.html                       # Toda la página (HTML semántico + Tailwind)
├── README.md                        # Instrucciones básicas
├── Documentacion.md                 # Este documento
└── .github/
    └── workflows/
        └── deploy.yml               # Workflow de despliegue en GitHub Pages
```

---

## 6. Cómo desarrollar

Al ser HTML puro no hay compilación: edita `index.html`, guarda y refresca el navegador.
Para un servidor local (opcional):

```powershell
npx serve .
```

## 7. Cómo se despliega

1. Se hace `git push` a la rama `main`.
2. GitHub Actions ejecuta el workflow **"Desplegar en GitHub Pages"**.
3. El sitio se publica en https://frisendo.github.io/ia-maker/

El estado de cada despliegue se consulta en la pestaña **Actions** del repositorio
(verde = publicado, rojo = error).

## 8. Personalización completada

- [x] Email de contacto real (`mailto:frisendo@gmail.com`)
- [x] Copyright del footer ("© 2026 Javier de Frutos")
- [x] URL de LinkedIn en el footer (https://www.linkedin.com/in/javier-de-frutos-torrijos-75468411/)
- [ ] Sustituir la tarjeta "Próximamente" por proyectos reales (pendiente, añadir cuando existan)
