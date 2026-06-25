# La Famiglia — Portal de Acceso y Comparativa de Agentes

## 👤 Datos del Estudiante

- **Nombre y Apellido:** [COMPLETAR]
- **Institución:** [COMPLETAR]
- **Asignatura:** [COMPLETAR]

## 🎭 Nota del Autor / Disclaimer

Elegí esta temática por gusto personal: soy fan de las películas de mafia, y quería que el proyecto no fuera "una landing más" sino algo divertido de hacer y de mostrar. De ahí surgió la idea de mezclar la elegancia oscura del cine de mafia con la estética lúdica de pixel art tipo Habbo Hotel, y de sumarle una parte interactiva —el Creador de Personaje— para que quien visite el sitio también pueda jugar un poco y armar su propio "mafioso". En general me gusta que las cosas que hago tengan ese costado descontracturado y divertido, y este trabajo fue una buena excusa para combinar eso con el objetivo técnico de la consigna: comparar la capacidad de resolución autónoma de dos agentes de IA.

## 🚀 Deploy Unificado

🔗 [COMPLETAR con el link de Vercel]

## 🤖 Prompt Exacto Utilizado

El prompt se elaboró de forma iterativa con la asistencia de **Claude (Sonnet 4.6) de Anthropic**, a través de muchos intercambios. La parte que más ajustes necesitó fue el Creador de Personaje: en los primeros intentos los avatares generados no se veían coherentes (partes del cuerpo desproporcionadas, sombreros mal construidos, elementos descentrados), por lo que hubo que reescribir varias veces las reglas de  construcción de cada parte (cabeza, torso, piernas, sombrero) hasta llegar a una versión suficientemente consistente.

Para la generación de las landing pages que se encuentran dentro de las carpetas correspondientes, se ejecutó exactamente el siguiente prompt en ambos agentes:

```
Rol
Actuá como un desarrollador Frontend Senior especializado en diseño temático, pixel art web y experiencias visuales inmersivas.

Task
<task>
Tu objetivo es desarrollar el código completo, funcional y en un único archivo HTML5 para La Famiglia — una landing page que recopila y presenta las mejores películas del género mafioso de la historia del cine, con una estética visual inspirada en el pixel art estilo Habbo Hotel: colores oscuros con detalles neón, tipografías bold y una identidad visual que contrasta lo elegante de la mafia con lo lúdico del pixel art. Todo el texto del sitio debe estar en español con ortografía correcta, incluyendo tildes y signos de puntuación.
</task>

Design system
<design_system>
Aplicá estrictamente la siguiente paleta usando CSS custom properties:
- --bg-main: #0d0d0d (negro profundo - fondo principal)
- --bg-card: #1a1a2e (azul noche - fondo de tarjetas)
- --neon-red: #ff2d55 (rojo neón - CTAs y acentos principales)
- --neon-gold: #ffd700 (dorado pixel - títulos, estrellas y detalles)
- --neon-cyan: #00f5ff (cyan neón - bordes activos, hover states)
- --text-crisp: #f0f0f0 (texto principal)
- --pixel-border: 2px solid (bordes estilo pixel, sin border-radius en elementos pixel art)

Tipografía: usá "Press Start 2P" de Google Fonts exclusivamente para el logo "La Famiglia" en el header y para los números de ranking. Para todos los demás textos usá "Share Tech Mono" a un mínimo de 14px. La estética pixel art se expresa a través de bordes cuadrados (border-radius: 0) en elementos clave y sombras box-shadow escalonadas.
</design_system>

Requirements
<requirements>
La Landing Page debe contener las siguientes secciones en este orden exacto:

1. Header: Barra de navegación sticky con el logo "La Famiglia" en "Press Start 2P" a la izquierda. Links de navegación al centro (Ranking, Personaje, Reseñas, Contacto) en "Share Tech Mono" a 14px mínimo. Botón CTA "Entrar a la Familia" a la derecha con estilo neón rojo.

2. Hero Section: El elemento visual decorativo debe ser una escena construida con CSS y divs en estilo pixel art que evoque de forma INMEDIATAMENTE RECONOCIBLE una de las escenas más icónicas de El Padrino: la oficina oscura de Vito Corleone (escritorio de madera oscura, sillón de respaldo alto, una lámpara con pantalla que ilumina el escritorio desde arriba, cortinas pesadas a los costados, luz tenue tipo persiana entrando de fondo, y un personaje mafioso sentado detrás del escritorio). La prioridad número uno es que cualquier persona que vea la escena diga "esto es la oficina de El Padrino", por sobre cualquier otro criterio técnico de perspectiva.

   Para dar sensación de profundidad y ambiente sin depender de una proyección isométrica 3D perfecta (que en intentos anteriores resultó en paredes mal alineadas o "abiertas"), usá estos recursos, más simples y confiables:
   - Un fondo de pared con gradiente oscuro (más claro en el centro, donde está el personaje, más oscuro hacia los bordes) para simular el foco de luz de la lámpara, en lugar de depender de paredes 3D rotadas.
   - Capas superpuestas en distintos planos (cortinas y sombras de fondo más atrás y más oscuras, escritorio y personaje más adelante, nítidos y con más contraste) para sugerir profundidad sin necesidad de rotaciones complejas.
   - Sombras proyectadas (box-shadow) debajo del escritorio, el sillón y el personaje para anclarlos visualmente al piso.
   - Si el agente puede lograr además dos paredes y un piso en ángulo isométrico correctamente cerrado (sin huecos, sin verse "abierto" hacia el espectador), genial, es un plus. Pero si no se puede garantizar que la perspectiva quede prolija, es preferible una escena más simple y plana, sin paredes en ángulo, antes que una habitación 3D rota, mal alineada o que no se entienda. La escena nunca debe sacrificar la legibilidad ("se entiende que es la oficina de El Padrino") a cambio de un efecto 3D que salga mal.
   - Usá pocos elementos pero bien resueltos y reconocibles (escritorio, sillón, lámpara, personaje, cortinas), con proporciones humanas correctas en el personaje (cabeza, torso y piernas claramente diferenciados, nunca un solo bloque de color).

   Incluí título principal "Las Películas que Definieron la Mafia", subtítulo descriptivo y dos CTAs ("Ver el Ranking" y "Crear mi Personaje").

3. Sobre La Famiglia: Sección breve explicando la misión del sitio: reunir y celebrar el mejor cine de mafia con una vuelta de tuerca visual única.

4. Ranking de Películas: Grid de 6 tarjetas (El Padrino, Goodfellas, Scarface, El Padrino II, Casino, Donnie Brasco). Cada tarjeta incluye: número de ranking en "Press Start 2P", título, año, director, puntuación con estrellas doradas (★), descripción corta de 2 líneas, y un personaje icónico de la película en pixel art lateral con CSS y divs. Los personajes deben tener proporciones correctas. Las tarjetas no deben tener ninguna animación de entrada ni efecto de aparición o desvanecimiento. Solo pueden tener efecto hover (box-shadow que crece al pasar el cursor).

5. Creador de Personaje Mafioso: El título de esta sección debe ser algo como "Armá tu personaje mafioso" — una frase directa y temática, sin mencionar términos técnicos. El usuario construye su avatar eligiendo:
- Tipo de cuerpo: Robusto, Delgado, Alto
- Color de piel: Claro, Medio, Oscuro
- Tipo de pelo: Corto liso, Rizado, Calvo
- Accesorio de cabeza: Sin accesorio, Sombrero fedora, Borsalino negro, Gorra
- Accesorio en el saco: Sin accesorio, Rosa roja (pequeño cuadrado rojo en el ojal)
- Ropa: Traje negro con corbata, Traje blanco, Campera de cuero negra

El avatar debe construirse con todas sus partes alineadas sobre el MISMO eje vertical central (cabeza, torso y piernas centrados entre sí, sin desplazamientos hacia un costado). Reglas específicas para evitar que el personaje salga deforme o desproporcionado:
- Estructura general apilada de arriba a abajo: accesorio de cabeza (si hay) → cabeza → torso → piernas, todos centrados horizontalmente respecto al contenedor del avatar.
- Cabeza: un cuadrado o rectángulo de tamaño fijo, con dos ojos simples (puntos o pequeños cuadrados) centrados en su mitad superior.
- Accesorios de cabeza (fedora, borsalino, gorra): cada uno debe construirse con AL MENOS dos partes apiladas y diferenciadas, no una sola franja plana: 1) una "copa" (la parte superior del sombrero, con algo de altura, de ancho similar o levemente menor al ala) apoyada directamente sobre la cabeza, y 2) un "ala" o visera (más ancha que la cabeza, fina, ubicada debajo de la copa, sobre la línea de los ojos). El ancho del ala no debe superar aproximadamente un 130-140% del ancho de la cabeza, para que no se vea como una tabla desproporcionada.
- Torso: un rectángulo más ancho que la cabeza (simulando hombros), centrado exactamente debajo de la cabeza. Si hay accesorio en el saco (rosa roja), debe ubicarse centrado en la mitad superior del torso (simulando el ojal sobre el pecho), nunca pegado a alguno de los bordes laterales.
- Piernas: dos rectángulos idénticos en tamaño, separados por un pequeño espacio centrado, ubicados simétricamente debajo del torso (el centro entre ambas piernas debe coincidir con el centro del torso y la cabeza). Las piernas deben tener una altura proporcional al resto del cuerpo (ni demasiado cortas ni asimétricas entre sí).
- Antes de finalizar, verificá que cabeza, torso y piernas comparten el mismo eje de simetría vertical; si alguna parte queda corrida hacia un costado respecto a las demás, corregilo.

Cada selección actualiza el avatar en tiempo real. Al hacer clic en "Unirme a la Famiglia" mostrar solo una frase aleatoria de entre 8 frases del cine de mafia, sin describir las opciones elegidas. Botón "Descargar mi personaje" usando html2canvas (CDN: https://cdnjs.cloudflare.com/ajax/libs/html2canvas/1.4.1/html2canvas.min.js) para exportar el avatar como PNG.

Es crítico que el avatar exportado mediante html2canvas se vea EXACTAMENTE igual al avatar mostrado en pantalla, en especial los accesorios de cabeza (sombreros). Para garantizarlo: construí cada accesorio de cabeza únicamente con elementos <div> reales (nunca con pseudo-elementos ::before/::after, ni con box-shadow para simular partes del sombrero, ni con filtros CSS o transformaciones que html2canvas pueda renderizar de forma inconsistente). Antes de invocar html2canvas, asegurate de que las fuentes y estilos estén completamente cargados (por ejemplo, esperando document.fonts.ready). Configurá la llamada a html2canvas con las opciones { backgroundColor: null, scale: 2, useCORS: true } para minimizar diferencias visuales entre la vista previa en pantalla y la imagen descargada.

6. Reseñas: Grid de al menos 3 tarjetas con nombre de usuario estilo Habbo, puntuación y comentario sobre su película favorita. Todas las tarjetas de esta sección deben tener exactamente el mismo tamaño (mismo ancho y mismo alto) entre sí, sin importar cuánto texto tenga cada comentario. Para lograrlo: usá una grilla con altura uniforme (display: grid con grid-auto-rows: 1fr, o flexbox con align-items: stretch), cada tarjeta con una altura fija o min-height idéntica para todas, estructura interna en flex-direction: column, y el texto del comentario limitado a un número fijo de líneas visibles (por ejemplo con -webkit-line-clamp) para que ningún comentario, por más largo que sea, modifique el tamaño final de la tarjeta.

7. Formulario de Contacto: Formulario centrado horizontalmente, con campos: nombre, email, película favorita, mensaje. Estilo pixel art dentro de contenedor tarjeta oscura. Botón de envío con efecto neón. Sin funcionalidad backend.

8. Footer: Logo, copyright "La Famiglia © 2026", links rápidos e íconos de redes sociales con estilo pixel. Los íconos deben iluminarse con glow neón al hacer hover (box-shadow + transition), cada uno con el color de su red social.
</requirements>

Technical constraints
<technical_constraints>
1. Cero dependencias locales: Solo CDN. Importá "Press Start 2P" y "Share Tech Mono" desde Google Fonts. Importá html2canvas desde cdnjs.cloudflare.com. Sin frameworks CSS externos.
2. CSS puro embebido: Todo en un bloque <style> en el <head>. Incluí @keyframes únicamente para parpadeo neón en bordes y hover en tarjetas. No incluir animaciones de fade-in, aparición ni desvanecimiento en las tarjetas del ranking.
3. JavaScript mínimo e inline: Solo para el creador de personaje, descarga con html2canvas y navegación. Todo en el mismo archivo.
4. Completitud estricta: Prohibido usar marcadores como <!-- resto del código -->. El archivo debe renderizarse perfectamente al abrirlo en el navegador.
5. Responsivo: Media queries nativas: grid de 3 columnas en desktop, 1 columna en mobile.
6. Contenido de tarjetas sin recortes: Cada tarjeta del ranking debe mostrar todo su contenido sin overflow ni texto cortado. Las tarjetas deben usar height: auto y overflow: visible para crecer según su contenido. Ningún texto debe quedar oculto o truncado bajo ninguna circunstancia. Esta regla aplica únicamente a las tarjetas del Ranking; las tarjetas de Reseñas, en cambio, deben tener todas el mismo tamaño fijo entre sí (ver punto 6 de Requirements).
7. Consistencia en exportación de imágenes: Cualquier elemento HTML que deba exportarse como imagen mediante html2canvas (el avatar del personaje) tiene que construirse evitando pseudo-elementos, filtros CSS y transformaciones complejas que html2canvas no soporte de forma confiable, para garantizar que el resultado descargado sea visualmente idéntico al elemento mostrado en pantalla.
</technical_constraints>

Output format
<output_format>
Devolvé ÚNICAMENTE el código HTML en un solo bloque. Sin explicaciones ni conclusiones. Tu respuesta debe empezar con <!DOCTYPE html> y terminar con </html>.
</output_format>
```

## 📸 Capturas de Pantalla

A continuación se detalla el flujo visual de la experiencia unificada:

**1. Portada de Acceso (Home)**
Página raíz que unifica los accesos al prompt y a las dos landing pages generadas de forma autónoma.
`01-home`

**2. Visor del Prompt Utilizado**
Detalle del prompt final estructurado con etiquetas semánticas (`<task>`, `<design_system>`, `<requirements>`, `<technical_constraints>`), disponible para su lectura desde la portada.
`02-prompt`

**3. La Famiglia — Agente Codex (GPT-5.5)**
Landing page completa. Se destaca la resolución de la escena Hero (oficina de Vito Corleone, reconocible e iluminada con gradiente) y el Creador de Personaje con proporciones correctas en cuerpo, sombrero y accesorios.
`03-codex-hero` · `03-codex-personaje`

**4. La Famiglia — Agente Antigravity (Gemini 3.5 Flash)**
Landing page completa. Resolvió el fondo del Hero de forma más sobria, sin texturas, pero sin perder la estética pixel art ni la legibilidad temática. El Creador de Personaje fue su punto más fuerte, con avatares mejor armados que en intentos anteriores.
`04-antigravity-hero` · `04-antigravity-personaje`

## 🛠️ Tecnologías del Proyecto

- **CSS3 puro** con custom properties (variables) para un sistema de diseño pixel art consistente en toda la landing.
- **Google Fonts** ("Press Start 2P", "Share Tech Mono") vía CDN.
- **html2canvas** (CDN) para la exportación del avatar del Creador de Personaje como imagen PNG.
- **JavaScript Vanilla (ES6+)** para la lógica del creador de personaje, la navegación y la descarga de la imagen.
- **CSS Grid & Flexbox** para los layouts responsivos del Ranking, las Reseñas y el Formulario de Contacto.
- **Pixel art 100% construido con `<div>` y CSS** (sin imágenes externas, sin sprites), incluyendo la escena ambientada del Hero y el avatar modular del Creador de Personaje.

## ⚠️ Alcance y Limitaciones del Proyecto

Tal como menciona la consigna (maquetado visual, sin funcionalidad backend), algunas partes del sitio son solo de demostración visual:

- Los links de navegación y los íconos de redes sociales del footer están maquetados, pero no llevan a ninguna URL real (son placeholders, `href="#"`).
- El Formulario de Contacto no envía ni persiste datos en ningún servidor; es únicamente maquetado visual.
- En el caso de Antigravity, los campos del formulario usan el atributo `required`, por lo que el propio navegador muestra su aviso nativo si se intenta enviar con algún campo vacío; al completarse correctamente, dispara además un `alert()` de confirmación de envío. Codex también usa `required` en sus campos, pero no agrega ningún mensaje de confirmación tras el envío.

## 🧠 Skills Utilizados y Análisis Comparativo

Siguiendo la restricción de la consigna de no modificar el código de forma manual, se evaluó el desempeño autónomo de ambos agentes ante exactamente el mismo prompt final.

🔸 **Desempeño del Agente Codex (GPT-5.5)**
- *Escena Hero:* resolvió la oficina de Vito Corleone aplicando un patrón de cuadrícula neón tileado (líneas rojas y cian repetidas) como fondo de toda la página, además de una animación continua de parpadeo neón (`@keyframes neon-flicker`) sobre la escena y el panel del Creador de Personaje, dándole una estética más cargada y "videojueguera".
- *Creador de Personaje:* logró una precisión geométrica notable: la cabeza, el sombrero, el torso, la corbata y las piernas comparten exactamente el mismo eje de centrado horizontal, calculado con offsets en píxeles. Modeló las piernas como dos rectángulos independientes separados por un espacio central, tal como pedía el prompt literalmente. Gestionó las variantes de cuerpo y ropa alternando clases CSS predefinidas (`body-slim`, `body-tall`, `outfit-white`, `outfit-leather`).
- *Detalle particular:* los íconos de redes sociales del footer son insignias de texto simples ("F", "X", "IG"), una resolución más austera que la de Antigravity en ese punto.

🔸 **Desempeño del Agente Antigravity (Gemini 3.5 Flash)**
- *Escena Hero:* optó por gradientes y bloques de color sólido en lugar de patrones de cuadrícula, logrando una estética más sobria y limpia sin perder ningún elemento pedido (escritorio, sillón, lámpara, persiana, cortinas).
- *Creador de Personaje:* centra automáticamente todas las partes del avatar usando flexbox (`display: flex; align-items: center`) en el contenedor, en lugar de calcular offsets manuales — una solución más robusta frente a cambios de tipo de cuerpo. Gestionó las variantes mediante CSS custom properties (`--torso-width`, `--legs-height`, etc.) actualizadas por JavaScript. Como diferencia de interpretación, modeló las piernas como un único bloque de pantalón con dos zapatos separados, en vez de dos piernas independientes con espacio entre ellas.
- *Detalle particular:* definió los íconos de redes sociales del footer con SVG vectorial real (Twitter/X, Instagram, Discord) en lugar de texto, más prolijos visualmente que las insignias de Codex.

Esta diferencia es uno de los hallazgos más relevantes del trabajo: ante exactamente las mismas instrucciones cada modelo eligió una técnica distinta para resolverlas (cálculo manual de offsets en Codex vs. centrado automático con flexbox y variables CSS en Antigravity), ambas válidas pero con beneficios distintos —la de Antigravity es más resistente a futuros cambios de diseño, mientras que la de Codex exige recalcular si se modifica el tamaño del avatar—. También se observan criterios estéticos distintos ante la misma consigna: Codex priorizó una atmósfera más texturizada y "ruidosa"; Antigravity priorizó la limpieza visual y el detalle vectorial en los íconos.

## 🛠️ Evaluación de Desafíos Técnicos Autónomos

El principal reto que debieron resolver de forma autónoma ambos agentes fue construir, únicamente con `<div>` y CSS (sin SVG ni imágenes, salvo los íconos sociales de Antigravity), dos piezas de pixel art con restricciones de proporción estrictas: una escena ambiental reconocible (la oficina de El Padrino) y un avatar modular con múltiples combinaciones de cuerpo, ropa y accesorios que debía mantenerse coherente en cualquier combinación elegida por el usuario.

- **Construcción de la escena:** el prompt original pedía una habitación isométrica completa con dos paredes y piso en perspectiva 3D real (técnica de "caja abierta" con `perspective` + `transform-style: preserve-3d`). Tras varias iteraciones en las que esa técnica resultó en paredes "abiertas" o mal alineadas, se simplificó la consigna priorizando la legibilidad temática por sobre la perfección de la perspectiva, lo cual permitió que ambos agentes resolvieran una escena reconocible usando recursos más simples (gradientes, capas superpuestas y sombras proyectadas) en lugar de transformaciones 3D complejas.
- **Centrado de las partes del avatar:** aunque el prompt pedía explícitamente que cabeza, torso y piernas compartieran el mismo eje vertical, cada agente resolvió esa restricción con una estrategia distinta (offsets manuales vs. flexbox + variables CSS), lo que demuestra que una misma instrucción de diseño puede derivar en arquitecturas de CSS muy diferentes según el modelo.
- **Construcción del sombrero en múltiples piezas:** ambos modelaron cada accesorio de cabeza con 2 o 3 partes diferenciadas según el tipo (ala y copa para fedora/borsalino, cuerpo y visera para la gorra), cumpliendo la regla de "al menos dos partes apiladas" pedida en el prompt para evitar que el sombrero se viera como una sola franja plana.
- **Consistencia en la exportación con html2canvas:** dado que esta librería puede renderizar de forma distinta ciertos estilos, el prompt exigió construir los accesorios únicamente con elementos reales, esperar a `document.fonts.ready` antes de exportar, y configurar `backgroundColor: null`, `scale: 2` y `useCORS: true`. Ambos agentes implementaron esta configuración de forma idéntica.
- **Tarjetas de tamaño uniforme:** en la sección de Reseñas, ambos agentes debieron resolver que tarjetas con comentarios de distinta longitud mantuvieran exactamente el mismo alto y ancho, mediante una combinación de grillas con altura uniforme (`grid-auto-rows: 1fr`) y limitación de líneas de texto (`-webkit-line-clamp`).
