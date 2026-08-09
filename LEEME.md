# TFANS · Propuesta de UI v2

Abre **`sistema.html`** primero (explica las decisiones) y luego **`index.html`** para navegar el prototipo.

## Qué pasaba con la v1

El lavanda de marca se estaba usando como relleno de casi todas las superficies. Eso provoca tres cosas: no hay jerarquía (todo pesa igual), el texto gris queda por debajo del contraste mínimo, y como algunas tarjetas eran oscuras y otras claras, cada pantalla parecía de un producto distinto. Las métricas llevaban iconos decorativos sin dato de referencia, y el contenido bloqueado usaba desenfoque, que es lo que hace todo el sector y además se puede revertir desde el navegador.

## La dirección

**Noir de alta gama** — es la expresión que ya aparecía en vuestra propia pantalla de «Nuestras creadoras». Fondo tinta berenjena, el lavanda vuelve a su papel de acento como en el logo, y el color se reserva para lo que hay que mirar: precio, botón y estado del contenido.

Sin un solo gradiente. Todos los colores son planos.

### Paleta

| Uso | Hex |
|---|---|
| Fondo de página | `#0C0710` |
| Barras y rail | `#140C1B` |
| Tarjetas | `#1B1124` |
| Filete / borde | `#31203D` |
| Violeta (acción) | `#8B2FD6` |
| Lila (dato clave) | `#C9A3F0` |
| Rosa (directo, propina) | `#FF8FCF` |
| Texto | `#F7F2FB` / `#9C8CAE` |

### Tipografía

- **Instrument Serif** — titulares, nombres de creadoras y precios. Da el aire editorial.
- **Archivo** — interfaz, botones y formularios.
- **JetBrains Mono** — cifras, horas, IDs y microetiquetas.
- **Poppins Extra Bold** — solo el logotipo, como hasta ahora.

### La firma: velo de trama

El contenido bloqueado no se difumina: se cubre con una trama de puntos violeta sobre tinta. Es opaca, plana, imposible de revertir desde el navegador y se reconoce de lejos como TFANS. Además codifica el estado en un vistazo:

- Sin velo → gratis
- Velo + «Con suscripción» → entra en el plan
- Velo + precio → pago aparte

## Pantallas incluidas

| Archivo | Pantalla |
|---|---|
| `index.html` | Portada pública |
| `explorar.html` | Explorar creadoras |
| `perfil.html` | Perfil de creadora |
| `inicio.html` | Feed del suscriptor |
| `mensajes.html` | Chat con contenido de pago |
| `suscripciones.html` | Mis suscripciones e historial |
| `pago.html` | Checkout + confirmación |
| `panel.html` | Panel de creadora |
| `publicar.html` | Nueva publicación |
| `ajustes.html` | Ajustes de cuenta |
| `verificacion.html` | Verificación de identidad |
| `admin.html` | Moderación, usuarios y auditoría |
| `sistema.html` | Sistema de diseño y criterios |

## Notas técnicas

- Un solo CSS: `assets/tfans.css`, con los tokens en `:root`. Cambiar la marca es cambiar seis variables.
- Sin dependencias ni build. Las fuentes vienen de Google Fonts (hace falta conexión la primera vez).
- Responsive hasta móvil, foco de teclado visible y `prefers-reduced-motion` respetado.
- Las imágenes son bloques de color generados por CSS, a propósito: así se ve la estructura sin que las fotos tapen los problemas de layout. En producción se sustituyen por `<img>` dentro de `.plate`.
