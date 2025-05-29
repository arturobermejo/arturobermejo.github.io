# Sistema de Blog Multiidioma / Multilingual Blog System

Este blog soporta contenido en inglés y español únicamente para la sección de blog. El resto del sitio (projects, music, about) permanece en inglés.

## Lógica de Visualización

- **Posts en inglés**: Siempre aparecen en la lista
- **Posts en español**: Solo aparecen en la lista si NO existe una versión en inglés del mismo post
- **Posts bilingües**: Solo la versión en inglés aparece en la lista, pero dentro del post hay un enlace a la versión en español

## Sistema de URLs Personalizadas

Ahora puedes personalizar completamente las URLs de ambos idiomas usando los parámetros `post_id` y `slug`:

- **`post_id`**: Identificador único que conecta las versiones en diferentes idiomas
- **`slug`**: Define la URL personalizada del post

## Cómo Crear Posts en Múltiples Idiomas

### 1. Post Solo en Inglés
```markdown
---
title: "My English Post"
date: 2024-01-15
draft: false
author: "Arturo Bermejo"
tags: ["tag1", "tag2"]
language: "en"
post_id: "unique-post-id"
slug: "my-custom-url"
---

Content in English...
```
**URL resultante**: `/blog/my-custom-url/`

### 2. Post Solo en Español
```markdown
---
title: "Mi Post en Español"
date: 2024-01-15
draft: false
author: "Arturo Bermejo"
tags: ["etiqueta1", "etiqueta2"]
language: "es"
post_id: "unique-post-id"
slug: "mi-url-personalizada"
---

Contenido en español...
```
**URL resultante**: `/blog/mi-url-personalizada/`

### 3. Post en Ambos Idiomas
Para posts que existen en ambos idiomas, usa el mismo `post_id` y URLs personalizadas:

**Archivo inglés** (`content/blog/welcome-post.md`):
```markdown
---
title: "Welcome to My Blog"
date: 2024-01-15
draft: false
author: "Arturo Bermejo"
tags: ["welcome", "introduction"]
language: "en"
post_id: "welcome-blog"
slug: "welcome-to-my-blog"
lang_link: "/blog/bienvenido-a-mi-blog/"
---
```
**URL**: `/blog/welcome-to-my-blog/`

**Archivo español** (`content/blog/bienvenido.md`):
```markdown
---
title: "Bienvenido a Mi Blog"
date: 2024-01-15
draft: false
author: "Arturo Bermejo"
tags: ["bienvenida", "introducción"]
language: "es"
post_id: "welcome-blog"
slug: "bienvenido-a-mi-blog"
lang_link: "/blog/welcome-to-my-blog/"
---
```
**URL**: `/blog/bienvenido-a-mi-blog/`

## Características

- ✅ Solo la sección de blog soporta múltiples idiomas
- ✅ El resto del sitio permanece en inglés
- ✅ Enlaces automáticos entre versiones de idiomas cuando existen ambas
- ✅ Posts en español solo aparecen en la lista si no hay versión en inglés
- ✅ Prioridad al inglés como idioma principal
- ✅ **URLs completamente personalizables** para ambos idiomas
- ✅ **Nombres de archivo flexibles** - no necesitas usar sufijos específicos

## Ejemplos de Comportamiento

### Caso 1: Post bilingüe con URLs personalizadas
- `welcome-post.md` (inglés) → `/blog/welcome-to-my-blog/` ← Aparece en la lista
- `bienvenido.md` (español) → `/blog/bienvenido-a-mi-blog/` ← NO aparece en la lista, pero accesible via enlace

### Caso 2: Post solo en español con URL personalizada
- `reflexiones-tecnologia.md` (español) → `/blog/reflexiones-tecnologia/` ← Aparece en la lista

### Caso 3: Post solo en inglés con URL personalizada
- `tech-tutorial.md` (inglés) → `/blog/advanced-web-development/` ← Aparece en la lista

## Estructura de Archivos

```
content/
└── blog/
    ├── _index.md
    ├── welcome-post.md                 # Inglés: /blog/welcome-to-my-blog/
    ├── bienvenido.md                   # Español: /blog/bienvenido-a-mi-blog/
    ├── tech-tutorial.md                # Solo inglés: /blog/advanced-web-development/
    └── reflexiones-tecnologia.md       # Solo español: /blog/reflexiones-tecnologia/
```

## Parámetros Importantes

- **`post_id`**: Debe ser idéntico en ambas versiones del mismo post
- **`slug`**: Define la URL final del post
- **`lang_link`**: URL completa al post en el otro idioma
- **`language`**: "en" para inglés, "es" para español

## Ventajas del Nuevo Sistema

1. **URLs semánticas**: Puedes usar URLs que tengan sentido en cada idioma
2. **Flexibilidad total**: No estás limitado a sufijos como `-es`
3. **SEO mejorado**: URLs más naturales en cada idioma
4. **Organización libre**: Los nombres de archivo pueden ser cualquier cosa 