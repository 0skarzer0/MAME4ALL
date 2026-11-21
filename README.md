# MAME4ALL

MAME para Dreamcast: adaptación a SDL de MAME4ALL (GP2X), de Chui.

MAME4ALL es un emulador de máquinas recreativas (Multi Arcade Machine Emulator) para Dreamcast: la adaptación a SDL de **MAME4ALL para GP2X** (Franxis) para Windows, GNU/Linux y Dreamcast, publicada por **Chui**. Este repositorio contiene su código fuente (beta 2), descomprimido.

> Archivo de preservación, no el desarrollo original. Los commits **no son de Chui**: cada uno reconstruye un paquete de fuentes publicado en su web.

## Contenido

- Raíz: `Makefile.dc`, `Makefile.gp2x`, `Makefile.linux`, `Makefile.psp`, `Makefile.win32`, `config.mk`, `objs.mk`.
- `src/` – código (`src/sdl/` es la capa SDL; `src/fame`, `src/raze`, `src/drz80`, `src/cz80`… los núcleos de CPU).

## Características

- Adaptación de MAME GP2X a SDL para Windows, GNU/Linux y Dreamcast.
- Núcleo FAME (Motorola 68000) y nuevo FAZE (Zilog Z80).
- Alrededor de 1000 juegos; MAME4ALL se divide en tres partes: Aged, Classic y Gold, con menú previo para elegir.
- Autoframeskip, 4 jugadores, caché de ficheros para cargar rápido y blitter escalado por hardware.
- Tarjeta SD para leer ROMs y guardar la configuración; selección 60-50 Hz en Dreamcast PAL.
- Artwork de DarkSlain; dos métodos de sonido (normal y preciso); menú de velocidad de CPU, sonido y mando.

## Port a NAOMI

Este código es el punto de partida de [`0skarzer0/mame4all-naomi`](https://github.com/0skarzer0/mame4all-naomi) (rama `naomi`), el port de MAME4ALL a la placa Sega NAOMI. Comparar con `diff -r` este repositorio y ese muestra qué se cambió para NAOMI.

## Historia de versiones

Un commit por paquete publicado, en orden cronológico (por la fecha de los ficheros de cada paquete), con una etiqueta por versión. Los commits llevan la fecha en que se crearon, no la de 2004-2011. El mensaje de cada commit incluye el SHA-256 del paquete original. 

| Etiqueta | Versión | Paquete original | Fecha del paquete |
|---|---|---|---|
| `beta-2` | beta 2 | `mame4all-beta2-src.tar.bz2` | 2011-04-05 |

## Compilar

Para Dreamcast se compila con [KallistiOS](https://github.com/KallistiOS/KallistiOS) usando `Makefile.dc`; hay Makefiles para GP2X, Linux, PSP y Windows. **Este repositorio no ha compilado ninguna versión**: es un archivo del código publicado.

## Origen

- Web original: *Chui's DC projects* (`chui.dcemu.co.uk`), recuperada de Internet Archive. Copia de la web con todos los proyectos: [Chui-s-Dreamcast-Projects.](https://github.com/0skarzer0/Chui-s-Dreamcast-Projects.) ([ver la página de MAME4ALL](https://htmlpreview.github.io/?https://github.com/0skarzer0/Chui-s-Dreamcast-Projects./blob/main/MAME4ALL/Chuis_DC_projects_MAME4ALL.html)).
- Los paquetes originales (`*.tar.bz2`, `*.rar`) siguen en ese repositorio, en `MAME4ALL/archivos/`. Esta historia se extrajo de allí con `git filter-repo` (`MAME4ALL/src`); por eso los mensajes de commit mencionan rutas de ese repositorio.

## Créditos

- **Chui** – adaptación a SDL y a Dreamcast (`src/sdl/minimal.h`: «SDL wrapper by Chui») y autor de la web original (`chui.dcemu.co.uk`).
- **Franxis** – autor de MAME4ALL para GP2X (comentarios «FRANXIS 2005-2006» por todo el código).
- **MAME** (Nicola Salmoria y el MAME Team) – el emulador original.
- **Fox68k** – FAME y FAZE, según la web de NEO4ALL.
- **DarkSlain** – artwork. **Juergen Buchmueller**, **Alex Pasadyn / Zsolt Vasvari**, **Richard Mitton** y **Stéphane Dallongeville** (`src/cz80`) – código de terceros, con sus avisos en cada fichero.
- **Internet Archive** (Wayback Machine) – de donde se recuperó la web.

## Licencia

Este repositorio no añade ninguna licencia. MAME se distribuye con la **licencia no comercial de MAME**, y el árbol mezcla además GPL (`src/gp2x`, `src/drz80/gpl.txt`) y ficheros «freeware para fines no comerciales» (`src/m6502`, `src/z80`, `src/raze`). Los avisos se conservan en cada fichero. Las marcas y los juegos pertenecen a sus propietarios.
