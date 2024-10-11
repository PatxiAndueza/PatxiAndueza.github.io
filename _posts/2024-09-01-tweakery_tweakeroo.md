---
title: Personalizando un Jekyll theme
ex-title: Tweakery tweakeroo
category: personal-web
tags: personal-web Jekyll TeXt
aside:
  toc: true
---
He tenido que hacer algunos *tweaks* al proyecto base de [TeXt Theme](https://kitian616.github.io/jekyll-TeXt-theme/) para acomodarlo a mis necesidades. En este post voy a explicarlos, para que el Patxi del futuro, cuando quiera hacer algún cambio, tenga anotados estos pequeños ajustes.

<!--more-->


## Idioma
El tema venía por defecto en inglés. No tenía soporte para español, así que lo he implementado guiándome por la [documentación](https://kitian616.github.io/jekyll-TeXt-theme/docs/en/i18n). Aun así, he decidido dejar algunas cosas en inglés.


### Implementar es-ES

Para hacerlo, he tenido que modificar varios archivos.

#### locale.yml

> El texto de los elementos de la interfaz de usuario se agrupa como un conjunto de claves de traducción en *_data/locale.yml*, lo que facilita la compatibilidad de TeXt con diferentes idiomas.

He localizado los componentes de la interfaz y los he añadido como conjunto de claves en el archivo para implementar el idioma:

```yml
[...]
## => Español
########################
es: &ES
  SUBSCRIBE               : "Suscribirse"
  READMORE                : "Leer más"
  [...]
  EMAIL_US                : "Envíanos un correo."
  COPYRIGHT_DATES         : "2024"

  es-ES:
  <<: *ES
```
#### nativation.yml, layouts y pages
>Utilizando «titles», puede definir un nombre multilingüe para el título de la página, el diseño y el navegador. TeXt define por defecto algunos nombres multi-idioma en _data/navigation, _layouts/archive, _layouts/home y about.md.

En el resto de los componentes con soporte para la internacionalización, he ido añadiendo las líneas en español correspondientes.
En *navigation.yml*, por cada elemento del menú de navegación:

```yml
  - titles:
      # @start locale config
      en      : &EN       About
      [...]
      es      : &ES       Sobre mí
      es-ES   : *ES
      [...]
      # @end locale config
    url: /about
```

En los *layouts* y en las páginas que correspondía, he añadido al *title*, en el *front matter*, la traducción al español correspondiente:

```yml
---
layout: article
titles:
  # @start locale config
  en      : &EN       About
  [...]
  es      : &ES       Sobre mí
  es-ES   : *ES
  [...]
  # @end locale config
  key: page-about
---
 [...]
```

#### _config.yml

Por último, después de estas modificaciones, he establecido el idioma por defecto de la web en es-ES:

```yml
[...]
 ## => Language and Timezone
##############################
lang: es-ES # the language of your site, default as "en"
```

### Elementos que dejo en en-US

Algunos elementos se quedan en inglés porque requiere más tiempo del que estoy dispuesto a invertir para modificarlo. Los meses en las fechas de publicación de los posts aparecen en inglés. En el apartado de Archivo, la opción "Show All" se mantiene esin tradución. Por ello, he decidido dejar las etiquetas de los posts en inglés para mantener la coherencia con este botón y porque aporta *flow*.

## Proyectos

Para personalizar la sección de "Proyectos", he realizado varias maniobras: colecciones personalizadas, modificación de elementos del tema y alguna triquiñuela. Quería tener una sección exclusiva para exponer mis trabajos, que no se mezclara con la parte principal/blog de la página y que tuviera un formato diferente, tanto dentro como fuera de los "posts".

### Crear la colección y hacerla visible

#### Collection

En la raíz de mi proyecto, he creado el directorio */_proyects*. Dentro de este, creo mis archivos Markdown que serán mis artículos. Para usar la [colección](https://jekyllrb.com/docs/collections/), la defino en *_config.yml*:

```yml
## => Colección custom
##############################
collections:
 projects:
    output: true
```

#### Presentar la coleción en la web

Para que el contenido que voy a incluir en esta *colection* esté disponible, tendré que crear una *page* con el *layout* "articles" cuya fuente de "article" sea la nueva colección. Además, quiero incluir la *page* en el menú de navegación. Así que creo y configuro la página *projects.md* en la raíz con los siguientes datos:

```markdown
---
layout: articles
title: Proyectos
articles:
  data_source: site.projects
  show_excerpt: true
  type: grid
permalink: /projects/
---
```
Y añado esta página en *navigation.yml* (con integración de idioma):
```yml
  - titles:
      # @start locale config
      en      : &EN       Projects
      es      : &ES       Proyectos
      es-ES   : *ES
      [...]
      # @end locale config
    url: /projects
```

### *Cover*s clickeables
<small>📝Añadido el 11/10/2024</small>

Para que las imágenes de portada de Proyectos sean clicables, he envuelto el *\<div>* que contiene la imagen con un *\<a>* en el archivo *_includes/article-list.html*:

```html
            <a href="{\{ \_\article_url }\}">
              <div class="card__image">
                <img src="{\{ _article_cover }\}" />
              </div>
            </a>
```

### *Layout* para proyectos

Quiero que los proyectos se sientan como vistas web independientes, como un todo. Por eso, a diferencia de los posts, no me gusta tener el "article-section-navigator" que permite saltar de uno a otro. Para evitar esto y seguir usando los "articles" del tema, he duplicado el layout *_layout/article.html* y lo he modificado como *_layout/project.html*:

```html
  [...]
  <div class="d-print-none">
    { - include article-footer.html - }
    <!-- Quito el navigator porque no quiero que salga siguiente/anterior -->
    <!-- { - include article-section-navigator.html - } -->
  </div>
  [...]
```

### Ñapa
 En la *page* /projects/, los "posts" se ordenan por fecha ascendente (de más antiguo a más nuevo), al contrario que en la *colection* principal. Por ese motivo, y porque no quiero que a los proyectos les aparezca la fecha de publicación del post, hago lo siguiente: asignarles una fecha solo para ordenarlos y ocultarla.

 ```markdown
---
show_date: false
date: 999-01-01
---
```

## Misc

Un par de detalles adicionales.

### *Path* de las imagenes

He decidido guardar mis imágenes con la siguiente estructura:

```
patxiandueza.github.io/
├─ _posts/
│  ├─ 📄 YYYY-MM-DD-title.md
├─ _projests/
│  ├─ 📄 title.md
├─ assets/
│  ├─ posts/
│  │  ├─ 🖼️ YYYY-MM-DD-name.png
│  ├─ proyects/
│  │  ├─ title/
│  │  │  ├─ 🖼️ name.png
│  ├─ ...
├─ _config.yml
├─ ...
```

### Logo y favicon

Siguiendo la documentación de TeXt, he utilizado [RealFaviconGenerator](https://realfavicongenerator.net/) para generar todos los favicons.

### Icono de correo

uBlock estaba bloqueando el icono del sobre de correo, así que lo he sustituido por uno local para evitar hacer peticiones a terceros. En *author-links.html*:

```html
    <li title="{{ _locale_string_email }}">
      <a class="button button--circle mail-button" itemprop="email" href="mailto:{{ _author.email }}" target="_blank">
        <!--  <i class="fas fa-envelope"></i> -->
        <div class="icon">{ - include svg/icon/social/mail.svg - }</div>  
      </a>
```

### Personalización del *theme*

Por último, siguiendo la excelente documentación de TeXt Theme, he añadido mis datos y personalizado el tema desde */_config.yml*.

---

Hola, Patxi del futuro. Soy Patxi del pasado dejándote esta nota. Espero que este post te sea útil, porque escribir esta documentación está siendo bastante una cosa.