# 📑 Reconstructor de PDFs Protegidos

Este script sirve para capturar las páginas de un PDF protegido en el visor de la ECAM y generar una versión lista para imprimir.

## 🚀 Cómo usarlo (Marcador)
Crea un nuevo marcador en tu navegador y en la URL pega este código comprimido:

```javascript
javascript:(async function(){ const viewer = window.PDFViewerApplication; if (!viewer) { alert("Abre el PDF primero."); return; } const totalPages = viewer.pagesCount; viewer.pdfViewer.currentScaleValue = "2.5"; const win = window.open("", "_blank"); win.document.write('<html><head><title>Captura PDF</title><style>@page { margin: 0; size: auto; } body { margin: 0; padding: 0; background: #222; } #container { display: flex; flex-direction: column; align-items: center; } .page-img { display: block; width: 100%; height: auto; } @media print { body { background: white; } .page-img { width: 100vw; height: 100vh; object-fit: contain; page-break-after: always; } #status { display: none; } }</style></head><body><div id="status" style="position:fixed; top:10px; left:10px; background:black; color:lime; padding:10px; z-index:9999;">Cargando...</div><div id="container"></div></body></html>'); const container = win.document.getElementById('container'); const status = win.document.getElementById('status'); for (let i = 1; i <= totalPages; i++) { status.innerText = `Procesando Página ${i} de ${totalPages}`; viewer.page = i; await new Promise(r => setTimeout(r, 2200)); const canvas = viewer.pdfViewer.getPageView(i - 1).canvas; if (canvas) { const img = win.document.createElement('img'); img.src = canvas.toDataURL('image/jpeg', 0.95); img.className = 'page-img'; container.appendChild(img); } else { i--; await new Promise(r => setTimeout(r, 1000)); } } status.innerHTML = "✅ LISTO! <button onclick='window.print()'>IMPRIMIR</button>"; win.focus(); })();
```

---

## 🛠️ Código Fuente (Para leer y editar)
Este es el mismo código pero formateado para que sea fácil de entender:

```javascript
/* 
   RECONSTRUCTOR DE PDF ECAM (VERSIÓN LEGIBLE)
*/
(async function() {
    const viewer = window.PDFViewerApplication;
    const totalPages = viewer.pagesCount;
    viewer.pdfViewer.currentScaleValue = "2.5"; 

    const win = window.open("", "_blank");
    // ... (resto del código que ya tenías)
})();
```
