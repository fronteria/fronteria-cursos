# FRONTERIA-CURSOS-SPEC.md

**Proyecto:** FronterIA Cursos  
**Versión de especificación:** 1.1 — 2026-10-20  
**Estado:** Implementación local inicial preparada; revisar antes de crear el repositorio remoto o desplegar.

## 1. Objetivo y alcance

Construir `https://cursos.fronteria.co` como portal público de apoyo a capacitaciones **presenciales para empresas** ofrecidas por FronterIA Software. No es un LMS ni un curso autónomo en esta versión. El portal presenta la oferta y sirve para consultar instrucciones, copiar prompts y descargar materiales durante y después del taller.

**Primer programa:** IA aplicada al trabajo de oficina en Logística y Comercio Internacional.  
**Niveles planificados:** Fundamentos (único disponible), Intermedio y Avanzado (futuros; no inventar temarios).  
**Edición inicial:** el material existente documenta el taller **INTRO de 4 horas**. Se publicará dentro del nivel Fundamentos como la edición disponible, sin afirmar que integra o cubre un nivel básico cuyos contenidos no están documentados.  
**Acceso:** público, sin autenticación ni inscripción obligatoria.  
**Idioma inicial:** español.  
**Público:** asistentes y personal administrativo no técnico de logística y comercio internacional.

### Fuera de alcance (v1)

Usuarios, login, pagos, progreso, exámenes automatizados, emisión de certificados, base de datos, backend Django/Railway, publicación de soluciones del instructor, contenidos ficticios para cursos futuros.

## 2. Repositorios y aislamiento

- **Fuente corporativa (referencia visual):** https://github.com/fronteria/fronteria-website
- **Sitio corporativo publicado (no modificar):** https://fronteria.co y https://www.fronteria.co
- **Repositorio de publicación corporativa existente (no modificar):** https://github.com/softwareinteligente/softwareinteligente.github.io
- **Nuevo repositorio sugerido:** `fronteria/fronteria-cursos`
- **Dominio nuevo:** `cursos.fronteria.co`

El portal de cursos tendrá **su propio proyecto Hugo, repositorio y despliegue**. No modificar archivos del repositorio corporativo ni configurar automáticamente su DNS. Preparar instrucciones para añadir más adelante un enlace «Cursos» al menú corporativo, pero no aplicarlo sin aprobación.

El repositorio corporativo local se inspeccionó. Está construido con Hugo y Ananke; presenta encabezados y pies oscuros, acentos dorados y enlaces azul claro. No declara una fuente de marca ni un logotipo dedicado. Se reutilizó `static/images/c3po-face.png` como imagen provisional por instrucción del propietario; reemplazarla luego por el logo o imagen definitiva. El portal usa plantillas propias y no depende del tema corporativo ni de rutas absolutas.

## 3. Diseño de información y rutas

Rutas canónicas para el portal:

```text
/
/cursos/
/cursos/ia-logistica-comercio-internacional/
/cursos/ia-logistica-comercio-internacional/fundamentos/
/cursos/ia-logistica-comercio-internacional/fundamentos/preparacion/
/cursos/ia-logistica-comercio-internacional/fundamentos/ejercicio-1/ … ejercicio-12/
/cursos/ia-logistica-comercio-internacional/fundamentos/recursos/
```
Las agrupaciones web son una **adaptación de navegación**, no una reescritura del cronograma. Mostrar un índice de ejercicios individuales 1–12 en sus grupos. Los cursos Intermedio y Avanzado podrán figurar como «Próximamente», sin enlaces a lecciones vacías ni descripciones inventadas.

### Página inicial

Marca FronterIA; presentación breve de capacitaciones presenciales para empresas; programa disponible; niveles; llamada a solicitar capacitación con los datos publicados: `contacto@fronteria.co` y WhatsApp `+57 315 449 0157`. No inventar otros datos de contacto. Enlace al sitio principal.

### Página de programa

Presentar los tres niveles, el estado de disponibilidad y el nivel Fundamentos como acceso al material existente. Evitar presentar los tres niveles como tres cursos ya impartidos.

### Página de Fundamentos

Ficha: duración **4 h incluidas dos pausas**, modalidad presencial, público administrativo sin experiencia técnica, metodología **20 % explicación / 80 % práctica**, 12 ejercicios (1–12), herramienta de IA gratuita (en el material se propone Claude; prompts utilizables con ChatGPT, Gemini o Copilot, sujetos a disponibilidad y límites). Mostrar objetivos fieles a la ficha y recursos.

### Páginas de lección

Título, objetivo (solo si está sustentado en el material), instrucciones, prompts copiable(s), archivos asociados, advertencias de verificación y botones «Anterior / Siguiente». Menú lateral o índice persistente en escritorio; menú accesible en móvil. No exigir que un visitante siga una secuencia obligatoria.

## 4. Material de origen y trazabilidad

**Entrada:** `Curso-IA-LogixComex-Intro-Claude.zip` (archivo entregado por el usuario). No suponer que Codex puede acceder automáticamente al adjunto de ChatGPT: el usuario deberá copiarlo al entorno de trabajo o a una carpeta local de importación. No subir el ZIP completo a un repositorio público porque contiene claves del instructor.

**Inventario verificado (11 archivos útiles):**

| Archivo de origen (nombre descriptivo) | Uso v1 | Publicación |
|---|---|---|
| `00_CursoIA-LogixComex…INTRO-FichaGeneral.pdf` | Fuente de ficha y cronograma | Revisar: es material operativo del instructor; no publicar por defecto |
| `00_CursoIA-LogixComex…INTRO-CuadernoParticipante.pdf` | Fuente principal de las lecciones y PDF de consulta | Público |
| `01_Fletes_y_Embarques.xlsx` | Ejercicios de Excel | Público |
| `02_Datos_Desordenados.xlsx` | Ejercicios de limpieza | Público |
| `03_Cadena_de_Correos.docx` | Ejercicio de correos | Público |
| `04_Carta_con_errores.docx` | Ejercicio de revisión | Público |
| `05_Contrato_Servicios.docx` | Ejercicio de resumen/revisión | Público |
| `06_Factura_Comercial.pdf` | Extracción de PDF | Público |
| `07_Packing_List.pdf` | Extracción de PDF | Público |
| `CLAVE_instructor_01_Fletes_y_Embarques.xlsx` | Soluciones | **Nunca público** |
| `CLAVE_instructor_02_Datos_Limpios.xlsx` | Soluciones | **Nunca público** |

Excluir archivos `.~lock.*`. Conservar originales descargables sin modificarlos; si se renombran para URL, preservar un manifiesto origen → destino. No agregar datos sensibles reales. Verificar que los archivos de práctica son ficticios antes de publicar.

**Nota:** el programa describe siete archivos de práctica (los siete numerados 01–07), además del cuaderno; las dos claves son privadas.

### Ejercicios verificados en el cuaderno

| Nº | Título de origen | Grupo de navegación |
|---:|---|---|
| 0 | Entrar y saludar | Correos y primeros pasos |
| 1 | Mal pedido contra buen pedido | Correos y primeros pasos |
| 2 | Cadena de correos | Correos |
| 3 | Seguimiento cordial y traducción | Correos |
| 4 | Cotización | Documentos |
| 5 | Revisar una carta | Documentos |
| 6 | Resumir un contrato | Documentos |
| 7 | Fórmulas en Excel | Excel y PDF |
| 8 | Limpiar datos desordenados | Excel y PDF |
| 9 | De PDF a Excel y verificación | Excel y PDF |
| 10 | Cazar el error | Verificación |
| 11 | Mi tarea real | Práctica final |

**Regla editorial crítica:** conservar las instrucciones y prompts originales, incluyendo marcadores editables entre corchetes, sin convertir ejemplos en hechos. El contenido web debe extraerse y adaptarse del cuaderno; el cronograma, objetivos y metodología se basan en la ficha. Si una lección no tiene material suficiente, mostrar la información existente y reportar la laguna en vez de inventarla.

## 5. Arquitectura Hugo

Usar Hugo actual y plantillas propias pequeñas, sin copiar Ananke. Priorizar Markdown y front matter; usar un shortcode de prompt y partials de navegación.

```text
fronteria-cursos/
├── hugo.toml
├── README.md
├── .github/workflows/deploy.yml
├── content/                  # inicio, programa, preparación y ejercicios 1–12
├── layouts/                  # plantillas propias, navegación y shortcode de prompt
├── assets/                   # CSS y JavaScript locales
├── static/                   # imagen provisional y recursos públicos permitidos
└── docs/                     # inventario, trazabilidad y despliegue
```

Usar un proyecto Hugo sencillo, Markdown y front matter para derivar listados y navegación. Configurar `baseURL = 'https://cursos.fronteria.co/'` y `locale = 'es-CO'`. Se permite una página por ejercicio; agrupar ejercicios en el índice por conveniencia, conservando su numeración original. Evitar duplicar contenido entre índices, menús y lecciones.

### Componentes

Usar Markdown estándar y un único componente reutilizable para los prompts con botón «Copiar» (JS pequeño y accesible, con alternativa cuando el portapapeles no esté disponible). Los enlaces de descarga y avisos pueden escribirse en Markdown; no crear shortcodes para cada elemento. No usar servicios externos innecesarios para renderizar el contenido.

## 6. Experiencia de usuario y accesibilidad

- Diseño responsive y consistente con la marca FronterIA, navegación clara para personal no técnico.
- Menú lateral en escritorio; índice colapsable accesible en móvil.
- Botones «Copiar prompt», «Descargar archivo», «Anterior», «Siguiente».
- Tipografía legible, contraste suficiente, foco visible, etiquetas descriptivas y uso completo por teclado.
- No publicar un índice de ejercicios sin enlaces operativos.
- Página de recursos con cuaderno PDF y los siete archivos de práctica.
- No depender de cuentas de IA ni de APIs para consultar el sitio.
- Aviso: no introducir datos confidenciales, verificar cifras y documentos, y considerar que funciones/límites de herramientas gratuitas pueden cambiar.

## 7. Seguridad y publicación

El repositorio de cursos y GitHub Pages son **públicos**. No incluir contraseñas, tokens, archivos `CLAVE_instructor_*`, documentos internos, datos reales de clientes ni fuentes administrativas. **No confiar en `.gitignore` como única barrera:** copiar al árbol público únicamente los archivos de una lista permitida y revisar `public/` antes de desplegar. Si un secreto llega a Git, retirarlo del historial según corresponda.

Antes de publicar, ejecutar Hugo y revisar que la salida no contenga nombres `CLAVE_instructor`, `.~lock`, archivos privados ni el ZIP. Comprobar los enlaces a los ocho recursos públicos y el índice de ejercicios 1–12. No añadir un verificador personalizado en v1; puede incorporarse cuando el flujo editorial lo justifique.

No usar Railway en v1.

## 8. Despliegue GitHub Pages

- No escribir el build en el repositorio corporativo ni en `softwareinteligente.github.io`. El remoto objetivo del portal es `fronteria/fronteria-cursos`.
- Documentar la habilitación de GitHub Pages en el nuevo repositorio, permisos necesarios y cómo se publica cada `git push`.
- Configurar dominio personalizado `cursos.fronteria.co` en Settings → Pages y el DNS **CNAME** en el proveedor DNS de `fronteria.co`, apuntando al hostname Pages que corresponda a la organización. En workflows personalizados, configurar el dominio en Settings; un archivo `CNAME` por sí solo no lo configura. Verificar el destino actual antes de aplicarlo; no tocar `fronteria.co` ni `www`.
- Verificar HTTPS y redirección esperada una vez propagado DNS.
- No prometer disponibilidad del subdominio hasta realizar el cambio de DNS y verificarlo.

## 9. Plan de implementación para Codex

**Fase 0 — Inspección:** completada con el código local de `fronteria-website` y el ZIP de materiales. Identidad visual de referencia: negro, dorado y azul claro; asset `c3po-face.png` solicitado como imagen temporal. Se conserva la ficha operativa y las claves solo como fuentes locales.

**Fase 1 — Esqueleto funcional:** completada localmente; home, catálogo, programa, Fundamentos, navegación responsive y componentes propios.

**Fase 2 — Migración editorial:** completada localmente; 12 ejercicios y prompts en Markdown; siete archivos de práctica y cuaderno descargables; claves excluidas.

**Fase 3 — Calidad:** Hugo construye; revisar responsive, navegación, accesibilidad, enlaces, copiar prompts, integridad del contenido y seguridad de publicación.

**Fase 4 — Entrega:** workflow Pages, documentación DNS y README de mantenimiento preparados. Entregar para revisión; no crear el repositorio remoto, publicar el dominio ni modificar el sitio corporativo en esta fase.

## 10. Criterios de aceptación

- [ ] `hugo` genera un sitio funcional sin errores.
- [ ] Home y catálogo público; solo Fundamentos disponible.
- [ ] Identidad visual inspirada en el repositorio corporativo, sin alterarlo.
- [ ] Contenido fiel al cuaderno y ficha del curso de 4 h.
- [ ] Ejercicios **1–12** navegables, con sus prompts e instrucciones.
- [ ] PDF del cuaderno y **siete** archivos de práctica descargables.
- [ ] **Ninguna** solución del instructor ni archivo temporal accesible o versionado públicamente.
- [ ] Botones de copia y enlaces de descarga probados.
- [ ] Uso correcto en escritorio y móvil, revisado en la validación visual disponible.
- [ ] README explica cómo editar Markdown, añadir recursos, agregar cursos y desplegar.

## 11. Instrucción inicial para Codex (copiar y pegar)

> Implementa el proyecto Hugo `fronteria-cursos` siguiendo íntegramente `FRONTERIA-CURSOS-SPEC.md`. Usa como referencia visual el repositorio `https://github.com/fronteria/fronteria-website`, cuya copia local ya está en el entorno; no lo modifiques. El material del primer curso se encuentra en `Curso-IA-LogixComex-Intro-Claude.zip` en el entorno de trabajo. Primero inspecciona el repositorio corporativo y el ZIP; después crea el portal con el contenido real del curso Fundamentos. Conserva los ejercicios 1–12 y sus prompts, con nombres de archivo y rutas que coincidan con la numeración visible; publica solo los siete archivos de práctica y el cuaderno, y excluye por completo las claves del instructor. Implementa componentes reutilizables y navegación responsive. No cambies DNS ni publiques en el dominio hasta que revise el resultado. Entrega un resumen de archivos creados, comandos de prueba, decisiones técnicas y pasos pendientes de publicación.

## 12. Decisiones diferidas

- Aprobación del diseño visual concreto tras ver el primer prototipo.
- Integración del enlace «Cursos» en el menú corporativo, en un cambio separado.
- Programa real de Intermedio y Avanzado.
- Fecha de lanzamiento y DNS definitivo.
