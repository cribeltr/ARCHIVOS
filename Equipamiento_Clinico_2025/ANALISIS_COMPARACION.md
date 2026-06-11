# Análisis: Reporte de equipos críticos 2025 vs nuevo protocolo (Carpeta 177)

**Hospital Dr. Hernán Henríquez Aravena — Subdepartamento Equipamiento Clínico**

## Archivos

| Archivo | Descripción |
|---|---|
| `Nuevo_Reporte_a_modificar_con_nuevo_protocolo_equipos_criticos_2025.xlsm` | Libro con 18 hojas de reportes técnicos de mantención preventiva de equipos críticos. |
| `177_Reporte_Ventiladores_Carpeta177.pdf` | Reporte técnico Carpeta N° 177 — Mantención preventiva Ventilador Mecánico Yuwell YH-830 (UPC Pediátrica), generado desde la hoja "Ventiladores" del libro. |

## Funcionamiento del libro

- Los datos de encabezado (Servicio, Equipo, Marca, Modelo, N° Serie, N° Inventario) se obtienen con `BUSCARV/VLOOKUP` contra el libro externo **PMP_2025** según el N° de carpeta. Ese libro externo **no está incluido**; sin él los encabezados no se resuelven.
- Varias hojas tienen un botón **IMPRIMIRCOPIAS** (macro VBA) que recorre las carpetas desde la celda `DESDE` hasta `HASTA` e imprime una copia por carpeta. Así se generó el PDF de la carpeta 177 (rango Ventiladores: 165 a 180).

## Estado de cada hoja respecto al nuevo protocolo

Características del **nuevo protocolo** (según el PDF Carpeta 177):
secciones de chequeo con estado *Pasa / Falla / N/A* + Observaciones; actividades de
mantenimiento con *Realizado / N/A* + Observaciones; estado final *"Equipo operativo /
Equipo fuera de servicio"*; nota *"Si no corresponde por tipo de equipo, se debe indicar N/A"*;
**4 firmas**: Empresa Convenio/Técnico Ejecutor, Técnico de Subdepartamento, Jefe
Subdepartamento, VºBº Profesional Servicio Clínico.

| Hoja | Estado |
|---|---|
| **Ventiladores** | ✅ Coincide exactamente con el PDF (nuevo protocolo ya aplicado). |
| **MAnestesia** | ✅ Formato nuevo protocolo, con ítems propios de anestesia (cilindros de respaldo, filtro de óxido nitroso). |
| **Diálisis** | ✅ Formato nuevo en chequeo, actividades y estado final. ⚠️ Solo 3 firmas: falta el bloque "VºBº Profesional Servicio Clínico". |
| **Incubadoras Semestral** | ⚠️ Híbrido: ya tiene las 4 firmas nuevas, pero el estado final sigue como "Equipo Operativo SI/NO" y no usa secciones de actividades con N/A. |
| **Incubadoras Trimestral** | ❌ Formato antiguo: estado final SI/NO, 3 firmas (sin Empresa Convenio). |
| **Monitores** | ❌ Formato antiguo: estado final SI/NO, 3 firmas, sin nota de N/A en encabezado, actividades sin columna N/A ni observaciones. |
| **Oximetro** | ❌ Formato antiguo (igual que Monitores). |
| **Desfibriladores** | ❌ Formato antiguo: estado final SI/NO, 3 firmas. |
| **DEA** (mensual) | ❌ Formato propio mensual con 2 firmas; estado final sin casillas Pasa/Falla. |
| **DEA-dia DEFIBTECH / DEA-G.P / DEA 1-3 SAMU / DEA-UEPI / DEA-CEM** | Planillas de monitoreo diario (formato distinto, chequeo día 1–31 por mes). |
| **INDICE** | Índice de hojas. No incluye las hojas "DEA 3-SAMU", "DEA-CEM 1 PISO" ni "DEA-CEM 3 PISO". |

## Pendiente por definir

Para actualizar las hojas en formato antiguo al nuevo protocolo se necesita definir,
por cada tipo de equipo, los ítems de chequeo y actividades del nuevo protocolo
(equivalentes a los del PDF de ventiladores), ya que son contenido técnico-clínico
específico de cada equipo.
