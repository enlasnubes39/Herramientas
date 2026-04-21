# 📽️ Manual: Descargar Grabaciones de Zoom (Método Maestro)

Si Zoom ha bloqueado la descarga directa y el método de Colab falla, sigue estos pasos para extraer el video usando las tripas del navegador.

## 🚀 Paso 0: Liberar el video (Si es una ventana emergente)
Si la ventana de Zoom se abre "recortada" y no ves tus marcadores o extensiones:
1. Pulsa `F12` -> pestaña **Console**.
2. Escribe `location.href` y pulsa Enter.
3. Copia el enlace resultante y pégalo en una pestaña **normal** de Chrome para recuperar tus herramientas.

## 🎯 Paso 1: Cazar el enlace real
1. Con el video abierto y reproduciéndose, pulsa `F12`.
2. Ve a la pestaña **Network** (Red).
3. En el filtro (el buscador pequeño arriba a la izquierda), escribe: `mp4`.
4. Busca la línea con el nombre del video (suele ser un nombre largo o empezar por GMT...) y haz **clic derecho** sobre ella.
5. Elige **Copy** -> **Copy as PowerShell**.

## 📝 Paso 2: Preparar la descarga
1. Abre el **Bloc de Notas** (Notepad).
2. Pega el código.
3. Ve al final de la **última línea** (la que empieza por `Invoke-WebRequest`).
4. Pon un **espacio** y añade esto al final:
   ` -OutFile "C:\Users\TRABAJO\Desktop\Clase_Zoom.mp4"`
   *(Puedes cambiar el nombre si quieres)*.

## ⚡ Paso 3: Ejecutar
1. Busca en Windows: **PowerShell**.
2. Pega todo el texto del Bloc de Notas y pulsa **Enter**.
3. Verás una franja azul indicando el progreso. ¡Cuando termine, el video estará en tu Escritorio!

---
> [!TIP]
> **¿Por qué este método?** Es infalible porque usa tu propia sesión y cookies. Para Zoom, es como si tu propio navegador estuviera guardando el video.
