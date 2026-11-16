# Guía de estilo · Web del Vivero de Empresas

Referencia para construir la web más tarde en HTML5 y CSS3 (un solo documento CSS compartido por todas las páginas). Recoge el diseño "Tu boceto con colores" del lienzo.

**Origen de cada decisión**

- Los colores del header, del banner, del fondo de la zona de tarjetas y del footer son los que indicaste en tu boceto a mano.
- El color de Incidencias, la tipografía, los tamaños y los espaciados los elegí yo. Tu boceto no los indicaba, así que puedes cambiarlos.

---

## 1. Colores

### Paleta principal (de tu boceto)

| Color | Hex | Dónde se usa |
|---|---|---|
| Azul noche | `#00111F` | Fondo del header. También texto principal, bordes de tarjetas y botón principal |
| Gris azulado claro | `#F1F5F9` | Fondo de la parte de texto del banner. También texto sobre header y footer |
| Gris azulado medio | `#CBD5E1` | Fondo de la zona de tarjetas (detrás de ellas) |
| Pizarra | `#334155` | Fondo del footer. También texto secundario |

### Colores de apoyo (decisión mía)

| Color | Hex | Dónde se usa |
|---|---|---|
| Ámbar suave | `#FDE68A` | Fondo de la tarjeta de Incidencias de instalación |
| Blanco | `#FFFFFF` | Fondo de las tarjetas y del bloque Detalles |
| Gris muy claro | `#E2E8F0` | Huecos de imagen, paneles de esquemas y fondo del visor de PDF |
| Gris medio | `#94A3B8` | Solo decorativo: iconos de imagen vacía y bordes del PDF. No usar para texto |

El #FF4500 que pusiste en Incidencias lo sustituí por el ámbar porque con texto blanco el contraste era de unos 3,4:1, que no llega a los 4,5:1 que se pide para texto normal. Con texto `#00111F` sobre el ámbar el contraste es mucho más alto.

### Contrastes (texto sobre fondo)

Valores aproximados. Todos superan el mínimo de 4,5:1 (WCAG AA).

| Texto | Fondo | Contraste |
|---|---|---|
| `#00111F` | `#FFFFFF` | 19:1 |
| `#00111F` | `#F1F5F9` | 17:1 |
| `#00111F` | `#FDE68A` | 15:1 |
| `#00111F` | `#CBD5E1` | 13:1 |
| `#F1F5F9` | `#00111F` | 17:1 |
| `#F1F5F9` | `#334155` | 9,5:1 |
| `#334155` | `#FFFFFF` | 10:1 |
| `#334155` | `#E2E8F0` | 8,4:1 |

### Variables CSS (opcional)

Si las defines una vez en el CSS y las usas en todo el sitio, cambiar un color es cambiar una línea:

```css
:root {
  --azul-noche: #00111F;
  --gris-claro: #F1F5F9;
  --gris-medio: #CBD5E1;
  --pizarra: #334155;
  --ambar: #FDE68A;
  --blanco: #FFFFFF;
  --gris-panel: #E2E8F0;
  --gris-deco: #94A3B8;
}
```

---

## 2. Tipografía

**Familia:** Lato (Google Fonts), con `system-ui, sans-serif` como alternativa.
**Pesos:** 400 (normal), 700 (negrita), 900 (extra negrita, para títulos).
**Origen:** elección mía. Tu boceto no indicaba tipografía.

Si la web se va a abrir sin conexión, descarga la fuente y enlázala desde la carpeta del proyecto en lugar de usar el enlace de Google Fonts.

| Elemento | Tamaño | Peso | Interlineado |
|---|---|---|---|
| Título de página (h1, en el banner) | 40 px | 900 | 1,15 |
| Título de bloque (h2: tarjetas, Detalles) | 22 px | 900 | 1,25 |
| Título de apartado (h3, dentro de Detalles) | 18 px | 900 | normal |
| Texto del banner | 17 px | 400 | 1,5 |
| Menú de navegación | 16 px | 400 (900 en la página activa) | normal |
| Botones y enlaces "Ver detalle" | 15 px | 700 | normal |
| Texto de apoyo (fechas, peso del PDF, etiquetas) | 13–14 px | 400 / 700 | normal |

Reglas útiles:

- Un solo `h1` por página.
- Los títulos siguen el orden h1, h2, h3 sin saltarse niveles.
- El texto de cuerpo no baja de 16 px en móvil.

---

## 3. Espaciados, bordes y tamaños

| Concepto | Valor |
|---|---|
| Ancho máximo del contenido | 1200 px, centrado |
| Margen lateral | 40 px |
| Separación entre tarjetas | 24 px |
| Padding interior de tarjetas | 24 px |
| Borde de tarjetas | 1,5 px sólido `#00111F` |
| Esquinas de tarjetas | 14 px |
| Esquinas de botones y paneles | 10 px |
| Altura mínima de botones y enlaces | 44 px |
| Logo | 56 × 56 px |
| Padding del header y del footer | 20 px y 24 px verticales, 40 px laterales |
| Altura del banner | 240 px mínimo en escritorio, 160 px en móvil |

---

## 4. Componentes

### Header
- Fondo `#00111F`, texto `#F1F5F9`.
- Logo a la izquierda, con enlace a ¿Qué ofrecemos?.
- Menú a la derecha, con texto sin caja y 28 px entre opciones.
- Página activa: peso 900 y subrayado de 3 px.
- Contacto: dentro de un óvalo con borde de 1,5 px `#F1F5F9`, texto en negrita.

### Banner
- Dividido en dos mitades. Izquierda: fondo `#F1F5F9`, título h1 y frase de presentación. Derecha: imagen real del vivero.
- Línea inferior de 1,5 px `#00111F`.
- En móvil las mitades se apilan y la imagen se oculta o se reduce.

### Zona de tarjetas
- Fondo `#CBD5E1`, tarjetas blancas.
- Rejilla de 3 columnas:
  - Fila 1: Infraestructura de red (2 columnas) + Equipamiento y almacenamiento (1).
  - Fila 2: Servicios en red (1) + Incidencias de instalación (2).
  - Fila 3: Despliegue en AWS (3).
- Cada tarjeta lleva título, texto breve, un hueco de imagen o esquema y el enlace "Ver detalle ↓".

### Tarjeta de Incidencias
- Fondo `#FDE68A`, texto `#00111F`.
- Lista de 3 filas con fecha, título de la incidencia y una flecha.
- Líneas de separación suaves, `rgba(0,17,31,0.25)`.
- Enlace final "Ver todas ↓".

### Detalles
- Bloque blanco con borde de 1,5 px `#00111F`.
- Un apartado por documento: título, resumen corto, peso del PDF y dos botones.
- **Ver documento:** fondo `#00111F`, texto `#F1F5F9`. Abre el PDF en un panel lateral.
- **Descargar PDF:** fondo blanco, borde `#00111F`, texto `#00111F`.
- Panel lateral del visor: unos 512 px de ancho, cabecera `#00111F` con título, botón Descargar y botón cerrar, y el PDF debajo sobre fondo `#E2E8F0`.

### Footer
- Fondo `#334155`, texto `#F1F5F9`.
- Logo a la izquierda, en el centro "Protección de datos" y la línea del autor, y a la derecha tres iconos de redes (IG, YT, TikTok) de 44 px redondos.

---

## 5. Responsive

- **Punto de corte principal:** 760 px. Por debajo, la rejilla pasa a 1 columna y todas las tarjetas ocupan el ancho completo.
- **Tablet (aprox. 760–1024 px):** 2 columnas. Infraestructura de red e Incidencias a ancho completo.
- **Orden en móvil:** el del enunciado: Infraestructura, Equipamiento, Servicios, Incidencias, Despliegue AWS.
- **Menú en móvil:** botón de menú desplegable. Aguanta cinco opciones.
- **Zonas táctiles:** mínimo 44 × 44 px, también en los iconos del footer.
- **Visor de PDF:** en móvil, "Ver documento" abre el PDF en otra pestaña o el panel ocupa toda la pantalla, porque muchos navegadores móviles no muestran bien un PDF incrustado.
- **Prueba:** comprobar el diseño a 360 px de ancho.

---

## 6. Pendiente de decidir

- Imagen real del banner.
- Nombre de quien hizo la página, para la línea de autor del footer.
- Cuántos PDF hay en realidad y cómo se llaman.
- Si el color ámbar de Incidencias te convence o prefieres otro.
- Si la tipografía Lato te gusta o prefieres otra.
- Si se mantiene el banner en las cinco páginas o solo en ¿Qué ofrecemos?.
- Diseño del resto de páginas (Empresas, Sostenibilidad, Ofertas de trabajo, Contacto), que aún no tienen wireframe.
