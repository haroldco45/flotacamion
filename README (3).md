# 🚛 Flota Distrileco — Sistema de Control de Vehículos

**Desarrollado por Vibras Positivas HM**  
Versión 1.0 — Mayo 2026

---

## Descripción

Sistema web de gestión de flota de camiones para **Distrileco Caucasia S.A.S.**, diseñado para controlar mantenimientos, documentos, conductores, talleres, gastos y generar reportes mensuales por vehículo.

Funciona como un archivo HTML único, sin servidor, sin internet y sin instalación. Los datos se guardan directamente en el navegador (localStorage).

---

## Módulos

| Módulo | Funcionalidad |
|---|---|
| 📊 Dashboard | Estadísticas generales, gasto del mes, alertas urgentes, últimos mantenimientos |
| 🚛 Vehículos | Ficha completa, documentos, km, conductor asignado, historial |
| 👤 Conductores | Datos, licencia, examen médico, vehículo asignado |
| 🔧 Talleres | Directorio de talleres mecánicos, eléctricos, lavaderos, etc. |
| 📋 Mantenimientos | Registro de visitas a talleres, repuestos, cambios de aceite, lavados |
| 💰 Gastos | Combustible, peajes, multas, seguros, trámites |
| 🔔 Alertas | Vencimientos automáticos de SOAT, tecnicomecanica, seguro, licencias |
| 📈 Reportes | Resumen mensual de gasto por vehículo exportable a CSV |

---

## Cómo usar

1. Abrir el archivo `distrileco-flota.html` en cualquier navegador (Chrome recomendado)
2. Los datos de demo vienen precargados — eliminarlos antes de uso en producción
3. Registrar primero: **Talleres → Conductores → Vehículos** → luego Mantenimientos y Gastos
4. Los datos se guardan automáticamente en el navegador

> ⚠️ Los datos están en el navegador donde se abre el archivo. Si se abre en otro computador o se borra el caché, los datos no estarán disponibles. Se recomienda exportar a CSV periódicamente como respaldo.

---

## Alertas automáticas

El sistema genera alertas cuando:

- Un documento (SOAT, Tecnicomecanica, Seguro, Tarjeta de Operación) vence en menos de **60 días** o ya está vencido
- La licencia de un conductor vence en menos de **60 días**
- El km actual de un vehículo está a **500 km o menos** del km programado para cambio de aceite

---

## Exportación

Desde el botón **📊 Exportar** (arriba a la derecha) se pueden descargar:

- Lista de vehículos
- Lista de conductores
- Historial de mantenimientos
- Historial de gastos
- Reporte completo (mantenimientos + gastos combinados)

Todos en formato `.csv` compatible con Excel.

---

## Datos que maneja el sistema

### Por Vehículo
- Placa, nombre/alias, marca, modelo (año), tipo, color, capacidad (toneladas)
- Kilometraje actual y km programado para próximo cambio de aceite
- Vencimientos: SOAT, Tecnicomecanica, Seguro Todo Riesgo, Tarjeta de Operación
- Conductor asignado, estado (Activo / En Taller / Inactivo)

### Por Conductor
- Nombre, cédula, teléfono, dirección
- Categoría de licencia y fecha de vencimiento
- Fecha de vencimiento del examen médico
- Vehículo asignado, estado

### Por Taller
- Nombre, tipo (mecánico, eléctrico, lavadero, etc.)
- Teléfono, dirección, contacto
- Servicios que ofrece, calificación (1–5 estrellas)

### Por Mantenimiento
- Vehículo, fecha, tipo de servicio, taller
- Km al ingreso, valor total, mano de obra
- Descripción del trabajo, repuestos utilizados
- Próximo mantenimiento (fecha y/o km), estado

### Por Gasto
- Vehículo, fecha, categoría, descripción, valor
- Categorías: Combustible, Peajes, Parqueadero, Multa, Lavado, Seguro, Impuesto, Documentos, Viáticos

---

## Tecnología

- HTML5 + CSS3 + JavaScript vanilla
- Sin dependencias externas (fuentes de Google Fonts en línea)
- Almacenamiento: `localStorage` del navegador
- Compatible con Chrome, Edge, Firefox

---

## Estructura del proyecto

```
flota-distrileco/
├── distrileco-flota.html   # Aplicación completa
└── README.md               # Este archivo
```

---

## Recomendaciones de uso

- Exportar CSV al final de cada mes como respaldo
- Mantener actualizado el km de cada vehículo después de cada viaje
- Registrar cada visita al taller el mismo día para que las alertas sean precisas
- Programar siempre el "próximo mantenimiento" al guardar cada servicio

---

## Comandos Git

```bash
# Primera vez
git init
git add .
git commit -m "Versión inicial sistema de flota Distrileco"
git remote add origin https://github.com/haroldco45/flota-distrileco.git
git branch -M main
git push -u origin main

# Actualizaciones
git add .
git commit -m "Descripción del cambio"
git push
```

---

## Créditos

**Desarrollada por Vibras Positivas HM — Derechos de Autor Reservados**  
Harold Marín · haroldco45@gmail.com · WhatsApp 3117700431  
Caucasia, Antioquia, Colombia — 2026
