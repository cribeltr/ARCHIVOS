# Generador de Reportes Técnicos — Ventiladores Mecánicos (MP 2026)

**Hospital Dr. Hernán Henríquez Aravena — Subdepartamento Equipamiento Clínico**

`Generador_Reportes_Ventiladores_2026.html` es una aplicación de una sola página,
**autocontenida y sin necesidad de internet** (los datos de los 180 ventiladores y los
logos van incrustados en el archivo). Reemplaza el flujo Excel + macro
`IMPRIMIRCOPIAS`: permite seleccionar la carpeta y generar el reporte técnico en PDF
con el mismo formato del nuevo protocolo (ej.: Carpeta 177).

## Cómo usarla

1. Abrir el archivo HTML con **Chrome o Edge** (doble clic).
2. Buscar el equipo por **carpeta, servicio, marca, serie o inventario** y
   seleccionarlo en la lista. La vista previa se actualiza al instante con los datos
   propios del equipo (Servicio, Equipo, Marca, Modelo, N° Serie, N° Inventario).
3. Opcional:
   - Elegir **Fecha** (si se deja vacía, la casilla se imprime en blanco para llenarla a mano).
   - Hacer **clic en las casillas** Pasa/Falla/N/A o Realizado/N/A para marcar una **X**.
   - Hacer clic sobre **Observaciones** (o la casilla Fecha) y escribir directamente.
4. Pulsar **«🖨 Generar PDF»**. En el diálogo de impresión:
   - Destino: **Guardar como PDF**
   - Papel: **A4**, márgenes: **predeterminados/ninguno**
   - Desactivar **«Encabezados y pies de página»**
   - El nombre sugerido del archivo será el N° de carpeta (ej.: `177.pdf`).

### Impresión por rango (equivalente al botón IMPRIMIRCOPIAS del Excel)

Indicar **desde / hasta** (ej.: 165 a 180) y pulsar **«🖨 PDF del rango»**: se genera un
solo PDF con un reporte por página por cada carpeta del rango.

## Origen de los datos

Los datos se extrajeron de la hoja `PMP_2026` (filas 174–353, ventiladores mecánicos,
carpetas 1 a 180) del archivo `Programacion_MP_2026.xlsm` incluido en esta carpeta.

- Carpetas **sin datos** en el PMP (se muestran como «SIN DATOS» y se imprimen con los
  campos en blanco): 12, 13, 14, 15, 18, 19, 20, 23, 24, 27, 31, 34, 36, 56, 57, 58,
  59, 68, 91, 94, 142, 155 y 176.

## Actualización de los datos

Si el PMP cambia (nuevos equipos, bajas, traslados), hay que regenerar la lista
embebida: los registros están en la constante `DATA` dentro del HTML (formato JSON,
una línea por equipo), donde también pueden corregirse valores puntuales con
cualquier editor de texto.
