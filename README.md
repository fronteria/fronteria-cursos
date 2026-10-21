# FronterIA Cursos

Portal estático de apoyo a talleres presenciales de IA aplicada a logística y comercio exterior. Construido con Hugo; el contenido se edita en Markdown y no necesita backend, cuentas, API ni dependencias de terceros en tiempo de consulta.

## LOG
2026/Oct/21: r1.01 Created local cursos website.
2026/Oct/20: r1.00 Initialized repo

## Requisitos y vista local

Se recomienda Hugo Extended. Para compilar:

```sh
hugo --minify
```

Para revisar localmente:

```sh
hugo server --buildDrafts
```

La URL local puede variar según la versión de Hugo; use la dirección que muestra el servidor.

## Editar contenido

- Inicio y ficha del programa: `content/`.
- Ejercicios: un archivo Markdown por ejercicio bajo `content/cursos/ia-logistica-comercio-internacional/fundamentos/`.
- Prompts copiables: shortcode `{{</* prompt */>}} ... {{</* /prompt */>}}`.
- Recursos descargables: `static/recursos/` y sus enlaces en `recursos.md`.
- Añadir futuros cursos como nuevas secciones bajo `content/cursos/`; publicar niveles solo cuando exista material aprobado.

## Seguridad de publicación

Los recursos se copiaron mediante lista permitida. Nunca copies al proyecto el ZIP original, archivos `CLAVE_instructor_*`, la ficha operativa ni temporales. Antes de subir o desplegar, revisa `public/` y confirma que solo contiene el cuaderno y los siete archivos de práctica autorizados.

## Identidad visual provisional

Se usó el nombre FronterIA y una paleta inspirada en el sitio corporativo (fondos oscuros, acento dorado y azul claro). La ilustración en `static/images/fronteria-mascota-provisional.png` fue copiada por instrucción del propietario y es provisional; reemplázala cuando haya un logo o recurso definitivo.

## Publicación

Lee [docs/DESPLIEGUE.md](docs/DESPLIEGUE.md) antes de crear el repositorio y activar GitHub Pages. Esta entrega no publica cambios ni configura DNS.
