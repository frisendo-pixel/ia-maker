# Landing Page Personal

Landing page personal estática: solo **HTML** y **Tailwind CSS** (vía CDN). Sin backend y sin base de datos.

## Características

- ✅ Estructura HTML **semántica** (`header`, `nav`, `main`, `section`, `article`, `footer`)
- ✅ Diseño **responsive** (menú móvil, grids fluidos)
- ✅ Estilos con **Tailwind CSS**
- ✅ Secciones: Inicio (hero), Sobre mí, Habilidades, Proyectos, Contacto
- ✅ Despliegue automático en **GitHub Pages** con GitHub Actions

## URL pública

https://frisendo.github.io/ia-maker/

## Desarrollo

Al ser HTML puro, basta con abrir `index.html` en el navegador o servir la carpeta:

```powershell
npx serve .
```

## Despliegue

Cada `push` a `main` ejecuta el workflow `.github/workflows/deploy.yml`, que publica el sitio en GitHub Pages.

> Nota: en el repositorio, activa **Settings → Pages → Source: GitHub Actions** si aún no está activado.
