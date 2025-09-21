### Excelente — plan para organizar Block Jumper y empezar a publicarlo en la web

A partir de la estructura actual, te propongo una reorganización mínima-viable que mantiene tu flujo creativo, pero te prepara para publicar por partes en `blockjumper.xyz`.

### Observaciones rápidas
- Hay contenido valioso pero disperso: `chapters/`, `characters/`, `arcos/`, `events/`, `monsters/`, `metadata/`, `comics/`, `notas/`.
- Nombres y rutas inconsistentes (`EpisodeX`, `EpisodeY`, `Chapters_all`, `alt_storys`), imágenes sueltas.
- Falta metadatos unificados para ordenar, filtrar, ocultar borradores y enlazar capítulos con personajes/arcos.

### Estructura propuesta (clara, extensible y lista para web)
- `content/` (nuevo hogar para todo lo publicable)
  - `chapters/` → por arco y orden
  - `characters/`
  - `lore/` → unifica `metadata/` y mundos
    - `factions/` (antes `groups`)
    - `places/`
    - `realms/` (antes `reinos`)
    - `axioms/` (antes `Axiomas.md`)
    - `weapons/` (antes `Armas_hash.md`)
    - `sports/`
  - `events/`
  - `monsters/`
  - `comics/`
  - `alt-universes/`
- `public/images/` → mover imágenes aquí y referenciarlas de forma relativa
- `notes/` → material privado/borradores (no se publica)
- `website/` → el sitio (Astro/Next), leyendo desde `content/`

Convenciones:
- Archivos en minúsculas, `kebab-case`, con sufijo de idioma: `.es.md` (ej: `001-despegue.es.md`).
- Imágenes co-localizadas o en `public/images/<tipo>/<slug>/...`.
- Un archivo = una entidad, con front matter consistente.

### Modelo de contenido (front matter)
En cada `.md` añade encabezado YAML para que el sitio y los scripts entiendan qué es, su orden y relaciones.

Ejemplo para capítulo:
```markdown
---
title: "Cohete Despega"
slug: "001-cohete-despega"
type: "chapter"
lang: "es"
status: "draft" # draft | published | private
arc: "saylor-capital"
order: 1
pov: ["Toshi 'Piggy' Banks"]
characters: ["toshi-piggy-banks", "dirk-newman"]
timeline: "Era 4 — Fuga temporal"
canonical_id: "chapter-001" # para enlazar futuras traducciones
tags: ["ciencia-ficcion", "politica", "tiempo"]
summary: "El despegue del cohete que revela la tecnología de energía futura."
created_at: "2025-08-17"
updated_at: "2025-08-17"
---
```

Ejemplo para personaje:
```markdown
---
title: "Toshi 'Piggy' Banks"
slug: "toshi-piggy-banks"
type: "character"
lang: "es"
status: "published"
affiliations: ["sitters"]
abilities: ["estratega", "tecnología temporal defensiva"]
antagonists: ["dirk-newman"]
tags: ["protagonista"]
summary: "Viene de una dimensión futura; enfrenta a Dirk, quien extrae energía del futuro."
---
```

### Mapas de migración (rápidos)
- `chapters/Chapter1.md` → `content/chapters/saylor-capital/001-cohete-despega.es.md`
- `chapters/EpisodeY.md` → `content/chapters/<arc>/00Y-<titulo>.es.md`
- `characters/PiggyBankz/Piggy_Bankz.md` → `content/characters/toshi-piggy-banks.es.md`
- `metadata/ReinosAll.md` → dividir en `content/lore/realms/*.es.md`
- `events/Situaciones.md` → dividir en eventos individuales en `content/events/*.es.md`
- `arcos/TheBattleOfTheForks.md` → `content/chapters/battle-of-the-forks/<n>-<titulo>.es.md` (o `content/lore/arcs/battle-of-the-forks.es.md` si es descripción del arco)
- `alt_storys/Sponge_revolution.md` → `content/alt-universes/sponge-revolution.es.md`

### Roadmap de publicación incremental (MVP → completo)
- Fase 1 (1–2 días): MVP público
  - Página principal: sinopsis del universo, 1 arco destacado, 2–3 personajes, 1 capítulo publicado.
  - Migrar 3–5 archivos clave con front matter y mover imágenes esenciales a `public/images`.
  - Filtrar por `status: published` para no mostrar borradores.
- Fase 2: Colecciones tipadas y búsqueda
  - Implementar colecciones (Astro Content Collections o Contentlayer) para `chapters`, `characters`, `lore`.
  - Página de personaje con “Aparece en” (lookup por `characters`).
  - Sitemap, OpenGraph y RSS.
- Fase 3: Arcos, timeline y SEO
  - Páginas de arco; timeline navegable por orden y `timeline`.
  - Internacionalización futura: `*.en.md` con `canonical_id` compartido.
- Fase 4: Comics y universos alternos
  - Secciones dedicadas con reader básico para `comics/` y `alt-universes/`.

### Stack recomendado (rápido, estático, fácil de mantener)
- Astro + Content Collections (lee `.md` con schemas tipados, excelente para narrativa).
- Despliegue en Vercel/Netlify; dominio `blockjumper.xyz` apuntando al sitio.
- Build CI (GitHub Actions) para validar front matter y lint de contenido.

Estructura del sitio:
- URLs:
  - `/es/` home
  - `/es/chapters/<arc>/<order>-<slug>`
  - `/es/personajes/<slug>`
  - `/es/lore/places/<slug>`, `/es/lore/realms/<slug>`, etc.
  - `/es/comics/<slug>`
- Solo publica `status: published`. Borradores visibles solo con preview token.

### Pasos inmediatos (concretos)
1) Crear carpeta destino
- `content/`, `public/images/`, `notes/`.
2) Migración mínima para publicar
- Mover y normalizar:
  - `Chapter1.md` → `content/chapters/<arc>/001-<slug>.es.md` con front matter.
  - `characters/PiggyBankz/Piggy_Bankz.md` → `content/characters/toshi-piggy-banks.es.md`.
  - 1 ficha de `lore/places/` (elige la más importante).
3) Etiquetar estados
- Añadir `status: published` a 1 capítulo + 2 personajes + 1 lugar; todo lo demás `draft`.
4) Bootstrapping del sitio
- Crear `website/` con Astro, colecciones `chapters`, `characters`, `lore`.
- Páginas: Home, Lista de capítulos, Ficha de personaje, Ficha de lugar.
5) Deploy
- Conectar repo a Vercel/Netlify, dominio `blockjumper.xyz`.
- Revisar SEO básico: `<title>`, OG, sitemap.

Si quieres, puedo generarte el esqueleto de `website/` y los schemas de contenido, y migrar 3 archivos con su front matter ahora.

### Opcional: comandos para arrancar el sitio (no ejecutados aún)
```bash
# 1) Crear sitio Astro
npm create astro@latest -- --yes /Users/aarontolentino/Documents/BlockJumper/code_blockJumper/website

# 2) Instalar integraciones útiles
cd /Users/aarontolentino/Documents/BlockJumper/code_blockJumper/website && \
npm i @astrojs/mdx @astrojs/sitemap

# 3) Crear enlace a contenido (si prefieres no mover archivos aún)
ln -s ../story /Users/aarontolentino/Documents/BlockJumper/code_blockJumper/website/content
```

¿Prefieres que migre ya 3 archivos clave y te deje `website/` listo para ver en local, o armamos primero los schemas y páginas base? 

- Sugerencias de primeros 3: `Chapter1.md` (capítulo), `characters/PiggyBankz/Piggy_Bankz.md` (personaje), `metadata/SaylorCapitalPlaces.md` dividido en 1–2 lugares importantes.

- Impacto:
  - Estructura clara y escalable (`content/` + front matter).
  - Publicación rápida por fases con control de borradores.
  - Sitio listo para crecer a multilenguaje y nuevas secciones.