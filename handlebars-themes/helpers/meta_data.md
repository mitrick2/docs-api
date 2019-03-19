---
title: "meta_data"
date: "2019-03-19"
meta_title: "Ghost Handlebars Theme Helpers: Meta Data"
meta_description: "How to access custom meta data properties in your Ghost theme, including meta title, meta description and custom canonical URLs. Read more 👉"
keywords:
    - meta
    - handlebars
    - themes
    - helpers
sidebar: "handlebars"
---


Usage: `{{meta_title}}` and `{{meta_description}}` and `{{canonical_url}}`

### Description

The meta data helpers are for outputting custom meta data that can be defined for any post or page using the meta data area of post settings. If no custom meta data is available, Ghost implements default meta titles and descriptions using the post content and a self-referencing canonical URL by default.

- `{{meta_title}}` – the meta title specified for the post or page in the post settings
- `{{meta_description}}` – the meta description specified for the post or page in the post settings
- `{{canonical_url}}` – the custom canonical URL set for the post - when set, this overrides the default self-referencing canonical URL 
