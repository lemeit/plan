# Plan Nutricional — Lemeit

Sitio de recetas y plan nutricional personal, con checklist interactivo de ingredientes, plan semanal y guía de pautas. Construido con [Astro](https://astro.build) y publicado en GitHub Pages.

🔗 **Sitio en vivo:** https://lemeit.github.io/plan/

## Qué incluye

- **`/recetas`** — 34 recetas (almuerzos/cenas y postres/desayunos), cada una con checklist de ingredientes que se guarda solo en el navegador, e impresión en PDF con formato prolijo.
- **`/plan-semanal`** — 4 semanas de almuerzos y cenas, en formato de tabla.
- **`/guia`** — reglas generales y sugerencias rápidas de desayunos y cenas.

## Estructura del proyecto

```text
/
├── public/
│   ├── favicon.svg       ← ícono de la pestaña del navegador
│   ├── marca.svg          ← logo usado en la home
│   └── img/                ← fotos de las recetas (una por receta, nombre = slug)
├── src/
│   ├── data/
│   │   ├── recetas.js         ← las 34 recetas (título, ingredientes, pasos, etc.)
│   │   └── plan-semanal.js    ← las 4 semanas del plan
│   ├── layouts/
│   │   └── Layout.astro       ← plantilla base (head, footer, estilos de impresión)
│   └── pages/
│       ├── index.astro           ← home
│       ├── guia.astro             ← pautas y sugerencias
│       ├── plan-semanal.astro     ← plan semanal
│       └── recetas/
│           ├── index.astro        ← índice de recetas
│           └── [slug].astro       ← plantilla de cada receta individual
└── package.json
```

Para agregar una receta nueva: sumar un objeto al array en `src/data/recetas.js` — la página se genera sola, sin tocar ningún otro archivo.

## Comandos

Todos se corren desde la raíz del proyecto:

| Comando           | Acción                                           |
| :----------------- | :----------------------------------------------- |
| `npm install`       | Instala las dependencias                          |
| `npm run dev`       | Levanta el servidor local en `localhost:4321`     |
| `npm run build`     | Compila el sitio de producción en `./dist/`       |
| `npm run preview`   | Previsualiza el build localmente antes de publicar |

## Despliegue

Cada `git push` a `main` dispara un build y deploy automático vía GitHub Actions, publicado en GitHub Pages.

## Licencia

El **código** de este proyecto está bajo licencia [MIT](./LICENSE). El **contenido** (recetas, plan nutricional) no está incluido en esa licencia — ver [`NOTICE.md`](./NOTICE.md) y el pie de página del sitio para el detalle de fuentes.