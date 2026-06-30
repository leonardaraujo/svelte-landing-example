# Guía mínima de SEO para Landing Page en SvelteKit

Esta guía sirve para mantener una landing page ordenada, rápida y entendible para buscadores como Google.

No significa que la página vaya a salir primera automáticamente, pero sí ayuda a cumplir lo mínimo para que el sitio tenga buena base técnica, buen contenido y una presentación correcta en buscadores y redes sociales.

---

## 1. Recomendación principal

Para una landing page usar preferiblemente:

```txt
SvelteKit + prerender/static generation
```

Evitar hacer la landing como una SPA vacía donde todo aparece solo después de cargar JavaScript.

Lo ideal es que el HTML principal ya salga renderizado cuando Google o cualquier usuario abra la página.

---

## 2. Activar prerender en SvelteKit

Crear o editar este archivo:

```txt
src/routes/+layout.js
```

Agregar:

```js
export const prerender = true;
```

Esto indica que las páginas se pueden generar como HTML estático.

---

## 3. Configuración recomendada para sitio estático

Instalar adapter static:

```bash
npm install -D @sveltejs/adapter-static
```

Editar:

```txt
svelte.config.js
```

Ejemplo:

```js
import adapter from '@sveltejs/adapter-static';

const config = {
  kit: {
    adapter: adapter({
      pages: 'build',
      assets: 'build',
      fallback: undefined,
      precompress: false,
      strict: true
    })
  }
};

export default config;
```

Luego construir:

```bash
npm run build
```

---

## 4. Metadata básica obligatoria por página

En cada página principal usar `<svelte:head>`.

Ejemplo:

```svelte
<svelte:head>
  <title>Nombre de la empresa | Servicio principal en ciudad o país</title>

  <meta
    name="description"
    content="Descripción clara de la empresa, servicio, beneficio principal y ubicación si aplica."
  />

  <link rel="canonical" href="https://tudominio.com/" />

  <meta property="og:title" content="Nombre de la empresa | Servicio principal" />
  <meta
    property="og:description"
    content="Descripción corta para cuando compartan la página en redes sociales."
  />
  <meta property="og:type" content="website" />
  <meta property="og:url" content="https://tudominio.com/" />
  <meta property="og:image" content="https://tudominio.com/og-image.jpg" />

  <meta name="twitter:card" content="summary_large_image" />
  <meta name="twitter:title" content="Nombre de la empresa | Servicio principal" />
  <meta
    name="twitter:description"
    content="Descripción corta para Twitter/X, WhatsApp y otras plataformas."
  />
  <meta name="twitter:image" content="https://tudominio.com/og-image.jpg" />
</svelte:head>
```

---

## 5. Plantilla SEO lista para una landing

Ejemplo para `src/routes/+page.svelte`:

```svelte
<svelte:head>
  <title>Mi Empresa | Soluciones digitales para negocios</title>

  <meta
    name="description"
    content="Creamos soluciones digitales rápidas, modernas y adaptadas a las necesidades de tu negocio. Conoce nuestros servicios y solicita una cotización."
  />

  <link rel="canonical" href="https://tudominio.com/" />

  <meta property="og:title" content="Mi Empresa | Soluciones digitales para negocios" />
  <meta
    property="og:description"
    content="Landing moderna para presentar servicios, generar confianza y captar nuevos clientes."
  />
  <meta property="og:type" content="website" />
  <meta property="og:url" content="https://tudominio.com/" />
  <meta property="og:image" content="https://tudominio.com/og-image.jpg" />

  <meta name="twitter:card" content="summary_large_image" />
  <meta name="twitter:title" content="Mi Empresa | Soluciones digitales para negocios" />
  <meta
    name="twitter:description"
    content="Soluciones digitales rápidas, modernas y enfocadas en resultados."
  />
  <meta name="twitter:image" content="https://tudominio.com/og-image.jpg" />
</svelte:head>

<main>
  <section class="hero">
    <p class="eyebrow">Soluciones digitales para negocios</p>

    <h1>Landing page moderna, rápida y preparada para buscadores</h1>

    <p>
      Presenta tu negocio con una página clara, profesional y optimizada para que
      tus clientes entiendan rápidamente qué ofreces y cómo contactarte.
    </p>

    <a href="#contacto">Solicitar información</a>
  </section>

  <section aria-labelledby="beneficios-title">
    <h2 id="beneficios-title">Beneficios principales</h2>

    <ul>
      <li>Diseño claro y enfocado en conversión.</li>
      <li>Estructura preparada para SEO básico.</li>
      <li>Carga rápida y navegación sencilla.</li>
      <li>Contenido organizado para generar confianza.</li>
    </ul>
  </section>

  <section aria-labelledby="servicios-title">
    <h2 id="servicios-title">Servicios</h2>

    <article>
      <h3>Diseño de landing page</h3>
      <p>
        Creamos una página de presentación clara para mostrar tu propuesta,
        beneficios y datos de contacto.
      </p>
    </article>

    <article>
      <h3>Optimización básica para buscadores</h3>
      <p>
        Organizamos títulos, descripciones, estructura HTML, imágenes y contenido
        para que la página sea más fácil de entender por Google.
      </p>
    </article>

    <article>
      <h3>Versión responsive</h3>
      <p>
        Adaptamos la página para que se vea correctamente en celular, tablet y escritorio.
      </p>
    </article>
  </section>

  <section aria-labelledby="confianza-title">
    <h2 id="confianza-title">Por qué trabajar con nosotros</h2>

    <p>
      Nos enfocamos en páginas simples, rápidas y profesionales. La prioridad es
      que el visitante entienda tu propuesta en pocos segundos y tenga una forma
      clara de contactarte.
    </p>
  </section>

  <section id="contacto" aria-labelledby="contacto-title">
    <h2 id="contacto-title">Contáctanos</h2>

    <p>
      Cuéntanos qué necesitas y te responderemos con una propuesta adaptada a tu negocio.
    </p>

    <a href="mailto:contacto@tudominio.com">contacto@tudominio.com</a>
  </section>
</main>
```

---

## 6. Reglas de contenido para una landing con buen SEO básico

### Título principal

Cada página debe tener un solo `h1`.

Ejemplo correcto:

```html
<h1>Landing page profesional para negocios en Perú</h1>
```

Evitar:

```html
<h1>Inicio</h1>
```

---

### Subtítulos

Usar los subtítulos en orden:

```txt
h1
h2
h3
```

No usar títulos solo para agrandar texto visualmente. Si es decoración, usar CSS.

---

### Texto real, no solo imágenes

Google necesita texto para entender la página.

Evitar una landing que sea solo:

```txt
imagen + botón + animaciones
```

Debe tener texto explicando:

```txt
Qué haces
Para quién lo haces
Qué problema resuelves
Qué beneficios das
Cómo te contactan
Dónde trabajas, si aplica
```

---

## 7. Checklist SEO mínimo

Antes de publicar revisar:

```txt
[ ] La página tiene un title único y claro.
[ ] La página tiene meta description.
[ ] Hay un solo h1.
[ ] Los h2 y h3 están bien ordenados.
[ ] El contenido explica claramente qué ofrece la empresa.
[ ] Hay llamadas a la acción visibles.
[ ] Las imágenes tienen atributo alt.
[ ] La página carga rápido.
[ ] La página se ve bien en celular.
[ ] Existe canonical URL.
[ ] Existe imagen OG para compartir en redes.
[ ] Existe robots.txt.
[ ] Existe sitemap.xml.
[ ] No hay textos importantes dentro de imágenes.
[ ] Los botones y enlaces son claros.
[ ] El sitio usa HTTPS.
[ ] Las URLs son limpias y simples.
```

---

## 8. Archivo robots.txt

Crear:

```txt
static/robots.txt
```

Contenido:

```txt
User-agent: *
Allow: /

Sitemap: https://tudominio.com/sitemap.xml
```

Cambiar `https://tudominio.com` por el dominio real.

---

## 9. Archivo sitemap.xml básico

Crear:

```txt
static/sitemap.xml
```

Contenido para una landing de una sola página:

```xml
<?xml version="1.0" encoding="UTF-8"?>
<urlset
  xmlns="http://www.sitemaps.org/schemas/sitemap/0.9"
>
  <url>
    <loc>https://tudominio.com/</loc>
    <lastmod>2026-06-30</lastmod>
    <changefreq>monthly</changefreq>
    <priority>1.0</priority>
  </url>
</urlset>
```

Cambiar:

```txt
https://tudominio.com/
```

por el dominio real.

---

## 10. Imagen para redes sociales

Agregar una imagen:

```txt
static/og-image.jpg
```

Tamaño recomendado:

```txt
1200 x 630 px
```

Debe verse bien cuando compartan la página por WhatsApp, Facebook, LinkedIn o Twitter/X.

---

## 11. Imágenes con alt

Ejemplo correcto:

```svelte
<img
  src="/equipo-trabajando.jpg"
  alt="Equipo desarrollando una landing page para un negocio"
/>
```

Evitar:

```svelte
<img src="/imagen1.jpg" alt="imagen" />
```

Si la imagen es decorativa:

```svelte
<img src="/decoracion.svg" alt="" />
```

---

## 12. URLs simples

Buenas URLs:

```txt
/
 /servicios
 /contacto
 /landing-page
```

Evitar URLs raras:

```txt
/page?id=123
/seccion-final-nueva-v2
/test-home-copy
```

---

## 13. Performance básica

Para que la landing cargue rápido:

```txt
[ ] Comprimir imágenes.
[ ] Usar formatos modernos como WebP cuando sea posible.
[ ] No usar videos pesados de fondo si no son necesarios.
[ ] No cargar muchas librerías externas.
[ ] No abusar de animaciones.
[ ] Evitar fuentes demasiado pesadas.
[ ] Revisar el sitio en celular.
```

---

## 14. Estructura recomendada para una landing

Una landing simple puede tener esta estructura:

```txt
Hero
Problema
Solución
Servicios o beneficios
Proceso de trabajo
Prueba social o confianza
Preguntas frecuentes
Contacto
Footer
```

Ejemplo:

```svelte
<main>
  <section>
    <h1>Servicio principal con beneficio claro</h1>
    <p>Explicación corta de qué haces y por qué importa.</p>
    <a href="#contacto">Solicitar información</a>
  </section>

  <section>
    <h2>Qué problema resolvemos</h2>
    <p>Describe el problema del cliente.</p>
  </section>

  <section>
    <h2>Cómo te ayudamos</h2>
    <p>Describe la solución de forma clara.</p>
  </section>

  <section>
    <h2>Servicios</h2>
    <article>
      <h3>Servicio 1</h3>
      <p>Descripción del servicio.</p>
    </article>
  </section>

  <section>
    <h2>Preguntas frecuentes</h2>
    <article>
      <h3>¿Cuánto demora el proyecto?</h3>
      <p>Depende del alcance, pero una landing simple puede desarrollarse rápidamente.</p>
    </article>
  </section>

  <section id="contacto">
    <h2>Contacto</h2>
    <p>Escríbenos para recibir más información.</p>
  </section>
</main>
```

---

## 15. Datos estructurados básicos JSON-LD

Opcional, pero recomendado.

Agregar dentro de `<svelte:head>`:

```svelte
<script type="application/ld+json">
  {JSON.stringify({
    '@context': 'https://schema.org',
    '@type': 'Organization',
    name: 'Mi Empresa',
    url: 'https://tudominio.com',
    logo: 'https://tudominio.com/logo.png',
    contactPoint: {
      '@type': 'ContactPoint',
      contactType: 'customer service',
      email: 'contacto@tudominio.com'
    }
  })}
</script>
```

Cambiar los datos por los reales.

---

## 16. Footer mínimo recomendado

```svelte
<footer>
  <p>© 2026 Mi Empresa. Todos los derechos reservados.</p>

  <nav aria-label="Enlaces legales">
    <a href="/politica-de-privacidad">Política de privacidad</a>
    <a href="/terminos">Términos y condiciones</a>
  </nav>
</footer>
```

Si la landing captura datos mediante formulario, agregar política de privacidad.

---

## 17. Cosas que NO debo hacer

```txt
[ ] No poner todo el texto dentro de imágenes.
[ ] No repetir el mismo h1 varias veces.
[ ] No usar títulos genéricos como "Inicio" o "Bienvenido".
[ ] No copiar contenido de otras páginas.
[ ] No llenar la página de palabras clave de forma artificial.
[ ] No bloquear Google en robots.txt.
[ ] No publicar sin revisar cómo se ve en celular.
[ ] No olvidar title y description.
[ ] No usar imágenes pesadas sin comprimir.
```

---

## 18. Ejemplo de buen title y description

### Para landing de desarrollo web

```html
<title>Desarrollo de landing pages para negocios | Mi Empresa</title>
<meta
  name="description"
  content="Creamos landing pages modernas, rápidas y adaptadas a negocios que buscan presentar sus servicios y recibir más contactos."
/>
```

### Para landing de restaurante

```html
<title>Restaurante de comida criolla en Lima | Nombre del Restaurante</title>
<meta
  name="description"
  content="Disfruta platos criollos preparados con ingredientes frescos. Conoce nuestra carta, ubicación y horarios de atención."
/>
```

### Para landing de servicio técnico

```html
<title>Servicio técnico de laptops en Lima | Nombre de la Empresa</title>
<meta
  name="description"
  content="Reparamos laptops, realizamos mantenimiento preventivo y solucionamos problemas de hardware y software en Lima."
/>
```

---

## 19. Comando final antes de publicar

Ejecutar:

```bash
npm run build
```

Si el build falla, corregir antes de subir.

Luego revisar manualmente:

```txt
[ ] La página abre correctamente.
[ ] El title aparece bien en la pestaña del navegador.
[ ] El diseño se ve bien en celular.
[ ] Los enlaces funcionan.
[ ] El formulario o botón de contacto funciona.
[ ] Las imágenes cargan.
[ ] No hay errores visibles en consola.
```

---

## 20. Objetivo final

La landing debe ser:

```txt
Clara
Rápida
Responsive
Fácil de entender
Fácil de contactar
Con buen title
Con buena description
Con HTML semántico
Con sitemap
Con robots.txt
Con imágenes optimizadas
```

SEO no es solo meter palabras clave.
SEO básico es ayudar al usuario y ayudar a Google a entender bien la página.
