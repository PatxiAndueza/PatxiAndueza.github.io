---
layout: project
title: Página web personal, escaparate de mis proyectos
permalink: /projects/web-personal

show_date: false
date: 998-01-01

aside:
  toc: true

cover: ..\assets\projects\web-personal\cover.png
---
<script src="https://code.iconify.design/iconify-icon/2.1.0/iconify-icon.min.js"></script>

## Introducción

### Antecedentes

Allá por 2022, estaba terminando la universidad, a punto de entrar al mercado laboral, y hacía poco había finalizado un proyecto de gran repercusión. Por estos motivos, decidí crear una *landing page* que también funcionara como currículum. Posiblemente inspirado por algún video *random* de YouTube y debido a que había estado trabajando recientemente con GitHub, opté por la opción de alojar la web en <iconify-icon icon="simple-icons:github"></iconify-icon> **GitHub Pages** y usar <iconify-icon icon="simple-icons:jekyll"></iconify-icon> **Jekyll** como "motor". El despliegue era (y sigue siendo) sencillo, el dominio no era terrible, y no me suponía ninguna inversión más que el tiempo que quisiera dedicarle. Además, con Jekyll, tenía la estructura, funcionamiento y estética de la web sin necesidad de hacer desarrollo web complejo.

Recuerdo haber pasado un rato buscando *themes* de Jekyll en GitHub, con la idea de encontrar uno con una estética minimalista que me sirviera como portafolio. Así fue como encontré [sproogen/resume-theme](https://github.com/sproogen/modern-resume-theme), añadí mis datos al único archivo de configuración que tenía la página, ¡y ya tenía mi sitio listo!

![Antigua landing](/assets/projects/web-personal/old-landing-web.png)

Poco después, maqueté un <iconify-icon icon="simple-icons:html5"></iconify-icon> **HTML** donde expuse mi proyecto [MiLuz](../projects/miluz), aunque quedó algo desconectado de la estética de la página. Ahora, con esta nueva versión de la web, lo he integrado de manera más coherente.

### Motivación

La motivación inicial para la antigua landing page era tener un portafolio y mostrar MiLuz. Pero, ¿qué es lo que motiva esta expansión/mejora/revisión de mi plataforma personal? Pues al igual que la vez anterior, otro proyecto: esta vez, [mi homelab](../projects/homelab). Estoy montando un *"servidor"* casero, y esto me genera la inquietud de querer documentarlo y mostrarlo. Quiero compartirlo con:

+ **Mi yo del futuro**: Uno de los principales objetivos de esta web es usarla como **biblioteca documental**.
  + ¿A quién no le ha pasado hacer una configuración específica para un problema muy particular, no anotar cómo lo hizo, y tiempo después no entender qué hizo su "yo" del pasado?
  + En la sección principal de esta web, el blog, voy a publicar los avances y las tecnologías que vaya implementando, para que, cuando quiera revisar alguna instalación, sepa **cómo** y **por qué** se configuró de esa manera.

+ ***Geeks***: Al igual que yo recurro a blogs y foros de gente apasionada por este tema para documentarme, me ilusiona pensar que, tal vez, algún día alguien lea lo que he escrito y le resulte útil.
  + Es una especie de "regalo" de vuelta a la comunidad, un aporte más a este nicho en internet.

+ **Observadores**: Y ya que estamos, esto también sirve como currículum. A quien quiera que esté *stalkeándome* LinkedIn podría interesarle ver que, después de trabajar todo el día con tecnología, sigo dedicando una parte de mi tiempo libre a hobbies relacionados con ella. 😉



## Desarrollo del Proyecto

Así pues, motivado por el nuevo proyecto y con ganas de darle un *lavado de cara* a la web (y con la intención de seguir usando **Git**, **GitHub Pages** y **Jekyll**), empecé —igual que la última vez— a buscar *themes* como un loco: un poco de ayuda de *ChatGPT* para filtrar ideas, repositorios de GitHub absurdamente ocultos bajo *tags* rarísimos, página tras página…

Al final, después de pelearme conmigo mismo para elegir uno, decidí seguir adelante con [**TeXt theme**](https://github.com/kitian616/jekyll-TeXt-theme) de *kitian616*.

> Estética limpia, personalizable, con muchas opciones para los artículos, maquetaciones de índices, secciones… y todo bien documentado.

Así que, después de pasar tiempo buscando un *theme*, hice lo que cualquier persona cuerda haría: pasar aún más tiempo **leyendo la documentación** del *theme* y *hacerme uno con él*.

Después de revisar las opciones que ofrecía y las características que quería que tuviese mi web, empezó **mi gran batalla**: varios días personalizando el *theme*.

La odisea está desarrollada en la [entrada del blog](/personal-web/2024/09/01/tweakery_tweakeroo.html) *"Personalizando un Jekyll theme"*, donde le explico (al Patxi del futuro) cómo implementé soporte para un idioma nuevo (`es-ES`), cómo creé y mostré una nueva colección, cómo personalicé las listas/índices... y alguna cosilla más.

Gracias a estas colecciones tengo dos secciones principales:
+ **Blog**: Donde suelto todo lo técnico. Escribo lo que aprendo, lo que configuro, y lo que quiero recordar. Si algo me costó, va aquí.
+ **Proyectos**: Aquí dejo mis proyectos bien presentados, con contexto, capturas y explicaciones. Básicamente, la parte bonita del portfolio.

![Secciones de la web](/assets/projects/web-personal/sections.png)

Además, integré **Iconify** porque quería iconitos. También explico cómo lo hice en esa misma [entrada del blog](/personal-web/2024/09/17/iconify.html).

Y, por último, después de dejar todo **como los chorros del oro**, hice lo más y lo menos divertido de todo:  
– **Lo más**: escribir mis aventuras desarrollando los proyectos, mientras exploraba todas las posibilidades que me ofrece *Markdown*.  
– **Lo menos**: documentar todo **al dedillo**.


<!--

connclusiones

y algo más estoy escribiendo esto x meses despues de haber documentado y menos mal que deje todo bien bonico para volver a el
-->

---

Web desarrollada con <iconify-icon icon="simple-icons:jekyll"></iconify-icon> **Jekyll** y alojada en <iconify-icon icon="simple-icons:github"></iconify-icon> **GitHub Pages**, utilizando un tema modificado para ajustarse a mis necesidades. El sitio está pensado como **archivo documental** y para presentar proyectos, tanto pasados como en desarrollo. Incluye una sección de blog para compartir pequeños avances y aprendizajes, además de un área dedicada a ofrecer una visión general de los proyectos. El control de versiones se gestiona con <iconify-icon icon="simple-icons:git"></iconify-icon> **Git** para mantener un seguimiento claro de los cambios.
