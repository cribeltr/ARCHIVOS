# Generador de Reportes Técnicos — Equipos Críticos (MP 2026)

**Hospital Dr. Hernán Henríquez Aravena — Subdepartamento Equipamiento Clínico**

`Generador_Reportes_2026.html` es una aplicación de una sola página, **autocontenida y
sin necesidad de internet** (datos de los equipos y logos van incrustados). Reemplaza el
flujo Excel + macro `IMPRIMIRCOPIAS`: se elige la **familia de equipos** y la **carpeta**,
y genera el reporte técnico de mantención preventiva en PDF, **idéntico al formato
original de cada familia** (verificado contra los PDF de ejemplo con desviación máxima
≤ 0,5 mm).

## Familias incluidas

| Familia | Carpetas | Equipos con datos |
|---|---|---|
| Ventiladores Mecánicos | 1–180 | 180 |
| Máquinas de Anestesia | 1–32 | 32 |
| Monitores Multiparámetros | 1–578 (bloque compartido) | 573 |
| Oxímetros de Pulso | (bloque monitores) | 4 |
| Desfibriladores | 1–93 (bloque compartido) | 75 |
| DEA | (bloque desfibriladores) | 18 |
| Incubadoras — Semestral | 1–41 | 41 |
| Incubadoras — Trimestral | 1–41 | 41 |
| Máquinas de Diálisis | 1–42 | 42 |

Los datos (Servicio, Equipo, Marca, Modelo, N° Serie, N° Inventario por carpeta) se
extrajeron de la hoja `PMP_2026` del archivo `Programacion_MP_2026.xlsm` incluido.

## Cómo usarla

1. Abrir `Generador_Reportes_2026.html` con **Chrome o Edge** (doble clic).
2. Elegir la **Familia** y luego la **Carpeta** (se puede filtrar con el buscador por
   carpeta, servicio, marca, serie o inventario). La vista previa se actualiza al instante.
3. Opcional: elegir **Fecha** (vacía = casilla en blanco para llenar a mano), marcar
   casillas con **clic** (X) o escribir observaciones directamente sobre el formulario.
4. **«🖨 Generar PDF»** → en el diálogo: destino **Guardar como PDF**, papel **A4**,
   márgenes predeterminados/ninguno, **sin** encabezados ni pies de página.
   El nombre sugerido es el N° de carpeta (ej.: `177.pdf`).
5. **«🖨 PDF del rango»**: un solo PDF con un reporte por página para cada carpeta del
   rango indicado (equivalente al botón `IMPRIMIRCOPIAS` del Excel).

## Carpetas de referencia

- `Ejemplos_originales/` — los 9 PDF de ejemplo entregados (uno por familia), usados
  como patrón de formato.
- `Muestras_generadas/` — los mismos 9 reportes generados con esta aplicación, para
  comparación.

## Actualización de los datos

Si el PMP cambia (equipos nuevos, bajas, traslados), hay que regenerar la constante
`DATA` embebida en el HTML (formato JSON por familia: `vent`, `anest`, `defdea`,
`incub`, `monox`, `dial`); también pueden corregirse valores puntuales con un editor
de texto.
