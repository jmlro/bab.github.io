# Bit a bit
Un blog sobre calidad del software

## Cómo crear posts

Los posts se crean en `_posts/` con el formato `YYYY-MM-DD-titulo.md`.

Usa `_posts/_template.md` como referencia.

Front matter:

```
---
title: "Título"
date: YYYY-MM-DD
layout: post
categories: categoria
---
```

## Cómo crear categorías

Para añadir una nueva categoría, crea un archivo en `category/nombre.md`:

```
---
title: "nombre"
layout: category
category: nombre
permalink: /category/nombre/
---
```

## Ver el blog en local

1. Instala Ruby y Bundler.
2. Ejecuta `bundle install`.
3. Ejecuta `bundle exec jekyll serve`.
4. Abre http://localhost:4000 en tu navegador.

## Publicar

Commit y push a main. GitHub Pages publica automáticamente.

