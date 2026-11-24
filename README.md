# GameStock Manager — PWA

Aplicación web instalable para administrar catálogo, inventario, tipo de cambio y ventas.

## Funciones incluidas
- Importación de Excel `.xlsx` / `.xls` y CSV (primera hoja del Excel).
- Detección flexible de columnas de producto, precio, stock, página/proveedor y plataforma.
- Agrupación por página/proveedor y búsqueda de productos.
- Precio original en USD y conversión a BOB con presets de tipo de cambio.
- Registro de ventas con descuento automático de stock.
- Anulación de ventas con devolución de unidades.
- Historial de ventas y exportación CSV.
- Accesos rápidos desde el dashboard, alta manual de productos y gráfico de ventas de los últimos 7 días.
- Respaldo y restauración JSON.
- Almacenamiento local mediante IndexedDB.
- PWA con service worker para volver a abrir el shell sin conexión después de la primera carga.

## Cómo probar
1. Descomprime la carpeta.
2. Publica su contenido en un hosting HTTPS (por ejemplo, GitHub Pages, Netlify o tu propio hosting).
3. Abre la dirección en Safari/Chrome.
4. En iPhone: Safari → Compartir → Añadir a pantalla de inicio.
5. En Android/PC: usa la opción Instalar aplicación cuando aparezca.

También puedes probarla localmente con un servidor estático, por ejemplo:
`python -m http.server 8000`
y abrir `http://localhost:8000`.

## Formato recomendado para Excel
La primera fila debe contener encabezados. Ejemplo:

| Producto | Página | Plataforma | Precio USD | Stock |
|---|---|---|---:|---:|
| Tekken 8 PS5 | PlayStation | PS5 | 35 | 5 |
| Mario Kart 8 | Nintendo | Switch | 40 | 3 |

Se reconocen encabezados equivalentes como `Nombre`, `Título`, `Juego`, `Price`, `Costo`, `Cantidad`, `Proveedor`, `Website`, `Consola`, etc.

## Importante
- Los datos se guardan en el navegador y dispositivo donde se usa la app. No existe sincronización entre dispositivos ni usuarios en esta primera versión.
- La librería de lectura Excel se carga desde jsDelivr. Para importar Excel por primera vez, se necesita conexión a internet; tras cargarla, el navegador puede conservarla en caché.
- La PWA requiere HTTPS (excepto localhost) para instalarse correctamente.
- Haz respaldos periódicos desde Configuración.
