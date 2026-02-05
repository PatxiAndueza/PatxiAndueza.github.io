---
title: Dominio personalizado en GitHub Pages
category: personal-web
tags: [personal-web, GitHub Pages]
hidden: false
aside:
  toc: false
---

<script src="https://code.iconify.design/iconify-icon/2.1.0/iconify-icon.min.js"></script>

Tenía la web funcionando en <iconify-icon icon="simple-icons:github"></iconify-icon> GitHub Pages con el dominio por defecto PatxiAndueza.github.io y, queriendo avivar la web de vuelta para documentar algún proyecto nuevo, he recordado que desde hace tiempo tengo el dominio **andueza.cloud** y que puedo usarlo.

<!--more-->

> El *.es* está pillado por una señora que probablemente no sabe ni que lo tenga.  
> Seguramente acens/Telefónica se lo metió en algún pack raro y ahí sigue, renovándose año tras año… y yo sin poder hacerme con él. 😡

## Objetivo

Pasar de `PatxiAndueza.github.io` a `patxi.andueza.cloud`.

To' guapo el nuevo dominio: *mi nombre* punto *mi apellido* punto  ☁️


## Proceso

Nada raro. Todo bastante de manual.


### Paso 1: Validar el dominio en GitHub (opcional)

Ir a <iconify-icon icon="fa7-solid:user-gear"></iconify-icon> Profile → Settings → Pages → Verified domains.

GitHub te da un registro TXT y un *value*. Lo añado en <iconify-icon icon="fa7-brands:cloudflare"></iconify-icon> Cloudflare (mi gestor DNS) y listo.

Es el clásico *challenge* de validación de dominio.  
Nada nuevo.


### Paso 2: Configurar el dominio personalizado en el repo

Con el dominio ya validado, en el repositorio <iconify-icon icon="fa7-solid:gear"></iconify-icon> Settings → Pages → Custom domain e introducir el dominio (en mi caso, subdominio).


### Paso 3: DNS en Cloudflare

En paralelo al paso anterior.

Crear una entrada CNAME desde el subdominio al dominio original.


## Paso 4: Esperar

5 minutillos para validación de GitHub y propagación.

- GitHub marca el dominio como válido
- El certificado HTTPS se genera solo
- La web empieza a responder en el dominio nuevo



## Conclusión

Proceso sencillo, bien documentado por GitHub y sin sorpresas raras.  

Y ahora sí: **patxi.andueza.cloud** en producción. 😌