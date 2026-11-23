# pbi-exportar-excel

Página estática que genera un archivo Excel (.xlsx) en el navegador a partir de los datos que envía una medida DAX desde un informe de Power BI publicado en la web.

Basado en [juansuas/PowerBIDownload](https://github.com/juansuas/PowerBIDownload).

## Uso

Un botón de Power BI con acción **URL web** apunta a una medida que devuelve:

```
https://fsaldarriaga-pbi.github.io/pbi-exportar-excel/exportar-excel.html#f=<archivo>&h=<hoja>&s=<notas>&e=<encabezado superior>&t=<tipos>&d=<datos>
```

| Parámetro | Contenido |
|---|---|
| `f` | Nombre del archivo, sin extensión |
| `h` | Nombre de la hoja (opcional) |
| `s` | Líneas de texto encima de la tabla, separadas por `%0A` (opcional; por ejemplo, los filtros aplicados) |
| `e` | Fila de encabezado superior, columnas separadas por `%09` (opcional); las celdas consecutivas con el mismo texto se combinan, por ejemplo un mes sobre sus columnas de valores |
| `t` | Un tipo por columna, separados por coma: `s` texto, `n` número, `i` entero, `m` moneda (negativos en rojo), `p` porcentaje (`0.25` = 25 %), `d` fecha (`yyyy-mm-dd` o `yyyy-mm-dd hh:nn`), `g` nivel de agrupación de la fila (`0`, `1`, `2`…: esa columna no se exporta y crea los botones +/- de Excel, con el resumen arriba) |
| `d` | Encabezados y filas; columnas separadas por `%09` y filas por `%0A` |

Los datos van en el fragmento (`#`), que el navegador no envía al servidor: no quedan en registros ni chocan con límites de longitud del servidor. Este repositorio no contiene datos.

## Prueba

[Descargar un Excel de ejemplo](exportar-excel.html#f=Ejemplo&h=Datos&t=s,n,d&d=PRODUCTO%09VALOR%09FECHA%0APolipropileno%20Homopol%C3%ADmero%0912345.60%092026-03-05%0A%C3%91and%C3%BA%20%C3%81cido%09-6%092026-04-01)
