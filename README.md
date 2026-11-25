# Doña Rosa – Concepto de rediseño web

Propuesta de rediseño **no oficial** del sitio web de Asados Doña Rosa, un restaurante de comida paisa con 40 años de historia y siete sedes. Es un proyecto de portafolio; no está afiliado al restaurante.

- **Concepto:** `index.html`
- **Caso de estudio (antes y después):** `caso.html`

## Qué mejora

| Aspecto | Antes | Después |
|---|---|---|
| Títulos principales (H1) | 17 | 1 |
| Imágenes sin descripción | 54 de 143 | 0 |
| Archivos que descarga la página | ≈ 250 | ≈ 15 |
| Contenido que se sale de la pantalla | Sí | No |
| Menú del restaurante en texto | No | Sí |

Medido el 24 y 25 de noviembre de 2026 en la página de inicio.

## Diseño

- Estructura inspirada en sitios de restaurantes nominados en Awwwards: tipografía con serifa grande (Gilda Display), texto que se desplaza, fotos dispersas, lista de platos que cambia la foto y botón de reserva flotante.
- Colores de la marca: blanco y rojo.
- Pensado primero para celular; las animaciones se apagan si el sistema pide reducir el movimiento.

## Asistente con IA

El botón **Pregúntale al asistente** abre un chat que responde preguntas sobre los platos, los precios para llevar y las sedes, en español o en inglés.

- **Cómo funciona:** la página le envía la conversación a un Google Apps Script (`asistente/Codigo.gs`). El script le pregunta a Gemini (`gemini-3.8-flash`, con `gemini-3.5-flash-lite` de respaldo) con instrucciones y datos fijos, y devuelve la respuesta.
- **Seguridad:** la clave de la API vive solo en las propiedades del script, nunca en la página. Las instrucciones y los datos también están en el script, así que nadie puede usar la clave para otra cosa.
- **Límites:** 300 preguntas al día y 12 por minuto entre todos los visitantes; mensajes de máximo 500 caracteres.
- **Sin inventar:** responde solo con la información del concepto. Lo que no está (horarios, teléfonos, precios de la carta) lo remite a la página oficial. No toma reservas ni pedidos.
- **Idioma:** el script detecta si la pregunta está en inglés y se lo indica al modelo.

## Cómo está hecho

HTML, CSS y JavaScript, sin plantillas ni frameworks, trabajando con IA (Claude). El asistente usa Google Apps Script y la API de Gemini (plan gratis).

## Créditos

- Información del negocio (historia, sedes, productos y precios para llevar): [página oficial](https://www.asadosdonarosa.com/), consultada el 25 de noviembre de 2026.
- Los platos de desayuno, almuerzo y parrilla son de ejemplo.
- Fotos de comida: Unsplash (Willian Reis, Gennady Zakharin, Marcos Paulo Prado, Alfredo Burgos, Usman Yousaf, Leila Issa y Alexandra Tran).
- La captura de la página actual se muestra solo para comparar; la marca pertenece a sus dueños.

Hecho por Pablo Ortiz Ochoa.
