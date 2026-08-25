# Gestión de Cobranzas — Cuenta Corriente

Herramienta web (HTML/CSS/JS, sin backend) para gestionar la cartera de deudas vencidas del laboratorio, a partir del reporte "Deudas vencidas" exportado desde Tango.

## Cómo usarla

Abrí `Gestion_Cobranza_AYMA.html` en el navegador (no necesita instalación ni servidor: es un archivo único, autocontenido).

## Funcionalidades

- **Cartera**: subí el `.xlsx` de deudas vencidas (hoja "Datos") y la herramienta:
  - Agrupa los clientes por vendedor (colapsable/expandible), mostrando subtotal y desglose por tramo de aging (0-30 / 31-60 / 61-90 / +90 días) al expandir.
  - Filtros con multiselección por vencimiento, vendedor y segmentación, más búsqueda por cliente/código y filtro de "en gestión".
  - Detalle de comprobantes por cliente, con subtotal por tramo.
- **Ventas**: permite cargar las ventas del último año de cada vendedor y calcula el coeficiente deuda vencida / ventas, con codificación de color según el nivel.
- **Gestión**: pasa clientes a gestión activa de cobranza, con seguimiento de saldo inicial/actual, % de recupero, estado y notas. Incluye exportación a CSV (tabla completa y formato para importar a Bigin/CRM).

Los datos (casos en gestión, ventas cargadas) se guardan en el `localStorage` del navegador — no se envían a ningún servidor.

## Reporte de origen (Tango)

Se espera un `.xlsx` con hoja **"Datos"** y, como mínimo, las columnas:

- Cliente
- Importe Pendiente (CTE)
- Nombre vendedor
- Fecha de vencimiento - Año / Mes / Día
- Segmentación (Adic. Cliente) — opcional
