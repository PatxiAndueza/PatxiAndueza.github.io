---
title: Side proyect: Servidor de Minecraft
ex-title: personal proyect
category: homelab
tags: [homelab, networking]
hidden: true
aside:
  toc: true
---
<script src="https://code.iconify.design/iconify-icon/2.1.0/iconify-icon.min.js"></script>

WIP

Antecedentes:
Side proyecto, tengo homelab parado.
Movivación:
Me han empezado a salir videos, se viene verano y quierpo jugar con los coleguis un survival de chill, hace un huevo de versiones que no toco y tengo ganas de exproralos.

Evaluación del proyecto:
Tengo un setup iudeal para un servidor de mc pequeño con gestión pro. De HW parto con un SER5 Mini PC
    CPU: Ryzen 5 5560U (6C/12T) → Más que suficiente, incluso para Fabric con algunos mods. Tiene margen para Crafty y tareas administrativas.
    RAM: 16 GB → Perfecta para correr Minecraft con mods + Crafty + servicios ligeros como SMB o Nginx Proxy Manager.
    Almacenamiento: 500 GB NVMe → Espacio de sobra para mundos grandes, backups y mods.
    Red: 1 Gbps LAN + WiFi 6 → Excelente para 3 jugadores, sin cuello de botella.

VOY AL PC VIEJO PROQUE SE ME HA MUERTO EL MINIPC

Objetivo:
    Minecraft modded (Fabric/Quilt), experiencia vanilla optimizada.
    Gestión con Crafty.
    Máximo 3 jugadores.
    Siempre encendido, posiblemente accesible desde fuera (uso de dominio y Cloudflare).

Resultado: el proyecto es perfectamente viable. Tienes una buena base para un servidor estable, autogestionado y limpio.

Con dominio y Cloudflare

Ya tener andueza.cloud en Cloudflare es una gran ventaja. Podrás:

    Exponer mc.andueza.cloud apuntando al servidor con DynDNS si es IP dinámica.

    Usar proxy de Cloudflare para proteger tu IP real (aunque cuidado con latencia).

    Configurar HTTPS para Crafty o cualquier panel.


Voy a intalerle un Debian 12 “Bookworm” Server.
Mi PC de jugar es un bazzite, me instalo de Popsicle de Systemn76 (los de Pop_OS!) para montar la imgen.
Descargo ISO. Flaseo la  ISO en el usb.
Recivo mi nuevo minipc y le voy a instalar debian 12
Instalación clasica, deshabilitar entorno de escritorio y habilitar servidor ssh
> mi rango dhcp es del 101 al 199, el router está en el .1 y voy a poner el servidor con la ip .10
Voy a intalarle cockpit, que un una interfaz web para la gestion de servidores, que hace tiempo leí sobre ella y me interesa problarla.

sudo apt update
sudo apt install cockpit -y

acceso a la consola vía, web y puedo ver los servicios activos y recursos. no necesito más

ahora estoy pensando en como montar el resto de cosas a nivel de red, que si ngix, proxy manaweb, si cuantos puertos quiero abrir, si usar un minecraft proxy como velocity, si quiero usar registros dns srv...

bueno, voy a instalar crafty coño

    "username": "admin",
    "password": "t@wcvt$m6O5Os3EIm$$ef0Kb0A@a#jsI4S@CGXhLv3y#TJGmo0R@7LcVySMEibu^",
    "info": "This is NOT where you change your password. This file is only a means to give you a default password."

instalamos adomptium java sdk21
estoy haciendo probas con velocity y me he montado una infraestructura guapa
sproxy, survival, creativo y flat
experto en añadir y configurar mods

Voy a escriptear porque ninguna de las soluciones que veo chuflan


subdominio poco fuzzeable
ddclient y a correr
 un poco de port forwardinf

tambien he configurado politca de backup schedule y retencion

no necesito un honeypot para ver que tengo intentos de conexion desde francia, alemania y NL, internet i guess?