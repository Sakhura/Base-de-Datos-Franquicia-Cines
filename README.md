# Base de Datos - Franquicia de Cines (CineDB)

## 📋 Descripción del Proyecto

Sistema integral de gestión para una franquicia de cines que permite administrar la operación completa de complejos cinematográficos, incluyendo películas, funciones, reservas, ventas, clientes y empleados.

## 🎯 Objetivos

- Gestionar múltiples complejos de cine en diferentes ciudades y países
- Administrar cartelera de películas y programación de funciones
- Controlar reservas y venta de boletos
- Gestionar ventas de productos (confitería)
- Implementar sistema de fidelización de clientes
- Generar reportes y análisis de negocio

## 🗂️ Estructura de la Base de Datos

### Tablas Principales (20 tablas)

| # | Tabla | Descripción |
|---|-------|-------------|
| 1 | **Paises** | Catálogo de países |
| 2 | **Ciudades** | Ciudades donde operan los cines |
| 3 | **Complejos** | Complejos cinematográficos (multiplex) |
| 4 | **Salas** | Salas de proyección por complejo |
| 5 | **Generos** | Géneros cinematográficos |
| 6 | **Clasificaciones** | Clasificaciones por edad |
| 7 | **Peliculas** | Catálogo de películas |
| 8 | **Pelicula_Genero** | Relación películas-géneros (M:N) |
| 9 | **Actores** | Catálogo de actores |
| 10 | **Pelicula_Actor** | Relación películas-actores (M:N) |
| 11 | **Funciones** | Programación de funciones |
| 12 | **Clientes** | Registro de clientes |
| 13 | **Membresias** | Tipos de membresías |
| 14 | **Cliente_Membresia** | Membresías activas de clientes |
| 15 | **Reservas** | Reservas de boletos |
| 16 | **Boletos** | Boletos generados |
| 17 | **Productos** | Catálogo de productos (confitería) |
| 18 | **Ventas** | Ventas de productos |
| 19 | **Detalle_Venta** | Detalle de productos vendidos |
| 20 | **Empleados** | Personal de los complejos |

## 🔧 Componentes del Sistema

### 📊 Vistas (20 vistas)

1. `v_cartelera_completa` - Películas en cartelera con información completa
2. `v_funciones_hoy` - Funciones programadas para hoy
3. `v_peliculas_con_elenco` - Películas con información del elenco
4. `v_reservas_activas` - Reservas confirmadas pendientes
5. `v_top_peliculas_mes` - Top 10 películas más vistas del mes
6. `v_productos_disponibles` - Catálogo de productos con stock
7. `v_clientes_vip` - Clientes con más puntos de fidelidad
8. `v_ocupacion_salas` - Estadísticas de ocupación por sala
9. `v_ventas_diarias` - Resumen de ventas diarias
10. `v_productos_mas_vendidos` - Ranking de productos
11. `v_empleados_activos` - Empleados activos por complejo
12. `v_historial_funciones` - Histórico de funciones realizadas
13. `v_membresias_activas` - Membresías vigentes
14. `v_ingresos_complejo` - Ingresos por complejo
15. `v_proximos_estrenos` - Películas próximas a estrenarse
16. `v_boletos_pendientes` - Boletos no utilizados
17. `v_estadisticas_genero` - Rendimiento por género
18. `v_analisis_precios` - Análisis de precios por tipo de sala
19. `v_clientes_frecuentes` - Clientes que más visitan
20. `v_dashboard_ejecutivo` - KPIs principales del negocio

### ⚙️ Stored Procedures (20 procedimientos)

1. `sp_crear_reserva` - Crear nueva reserva de boletos
2. `sp_confirmar_reserva` - Confirmar reserva y generar boletos
3. `sp_cancelar_reserva` - Cancelar reserva y liberar asientos
4. `sp_buscar_funciones` - Buscar funciones disponibles
5. `sp_registrar_venta` - Iniciar venta de productos
6. `sp_agregar_producto_venta` - Agregar producto a venta
7. `sp_finalizar_venta` - Completar venta y calcular totales
8. `sp_peliculas_en_cartelera` - Obtener cartelera actual
9. `sp_reporte_ventas` - Reporte de ventas por período
10. `sp_top_peliculas` - Top películas más vistas
11. `sp_actualizar_puntos_cliente` - Actualizar puntos de fidelidad
12. `sp_verificar_disponibilidad_sala` - Verificar disponibilidad de sala
13. `sp_programar_funcion` - Programar nueva función
14. `sp_historial_cliente` - Historial de reservas del cliente
15. `sp_productos_mas_vendidos` - Productos más vendidos
16. `sp_ocupacion_salas` - Ocupación de salas por complejo
17. `sp_validar_boleto` - Validar y usar boleto
18. `sp_reporte_empleados` - Reporte de empleados
19. `sp_estadisticas_generales` - Estadísticas generales
20. `sp_buscar_peliculas` - Búsqueda avanzada de películas

### 🔔 Triggers (25 triggers)

1. `trg_validar_capacidad_reserva` - Validar disponibilidad antes de reservar
2. `trg_actualizar_asientos_reserva` - Actualizar asientos al reservar
3. `trg_restaurar_asientos_cancelacion` - Restaurar asientos al cancelar
4. `trg_validar_stock_venta` - Validar stock antes de vender
5. `trg_actualizar_stock_venta` - Actualizar stock después de venta
6. `trg_calcular_subtotal_detalle` - Calcular subtotal automáticamente
7. `trg_actualizar_total_venta` - Actualizar total de venta
8. `trg_agregar_puntos_fidelidad` - Agregar puntos al completar reserva
9. `trg_validar_fechas_membresia` - Validar fechas de membresía
10. `trg_actualizar_estado_membresia` - Actualizar estado de membresía
11. `trg_validar_horarios_funcion` - Validar conflictos de horarios
12. `trg_generar_codigo_reserva` - Generar código único de reserva
13. `trg_validar_edad_boleto` - Validar edad según clasificación
14. `trg_generar_qr_boleto` - Generar código QR automático
15. `trg_actualizar_estado_funcion` - Actualizar estado según fecha
16. `trg_validar_precio_funcion` - Validar rangos de precio
17. `trg_prevenir_eliminar_reserva` - Prevenir eliminación de reservas
18. `trg_auditoria_peliculas` - Auditoría de cambios
19. `trg_validar_capacidad_sala` - Validar capacidad de sala
20. `trg_calcular_expiracion_reserva` - Calcular fecha de expiración
21. `trg_validar_metodo_pago` - Validar método de pago
22. `trg_proteger_boletos_usados` - Proteger boletos usados
23. `trg_validar_descuento_membresia` - Validar descuentos
24. `trg_registrar_uso_boleto` - Registrar hora de uso
25. `trg_validar_duracion_pelicula` - Validar duración

### 📑 Índices

- **Índices simples**: Para optimizar búsquedas frecuentes
- **Índices compuestos**: Para consultas complejas
- **Índices de claves foráneas**: Para mejorar joins

## 🚀 Instalación

### Requisitos Previos

- MySQL 8.0 o superior
- MySQL Workbench (recomendado)

### Pasos de Instalación

1. **Crear la base de datos y tablas**
```sql
SOURCE franquicia_cines.txt;
```

2. **Insertar datos de prueba**
```sql
SOURCE Cine_db_inserts.txt;
```

3. **Crear índices**
```sql
SOURCE indices.txt;
```

4. **Crear vistas**
```sql
SOURCE vistas.txt;
```

5. **Crear stored procedures**
```sql
SOURCE sp_cine.txt;
```

6. **Crear triggers**
```sql
SOURCE trigger.txt;
```

## 📖 Uso del Sistema

### Ejemplos de Consultas

#### Consultar cartelera actual
```sql
SELECT * FROM v_cartelera_completa;
```

#### Crear una reserva
```sql
CALL sp_crear_reserva(1, 5, 2, @id_reserva, @codigo);
SELECT @id_reserva, @codigo;
```

#### Ver top películas
```sql
CALL sp_top_peliculas('2024-01-01', '2024-12-31');
```

#### Consultar ocupación de salas
```sql
SELECT * FROM v_ocupacion_salas 
WHERE nombre_complejo = 'CinePlex Hollywood';
```

## 📊 Diagrama de Relaciones

```
Paises → Ciudades → Complejos → Salas → Funciones
                                           ↓
Peliculas ← Pelicula_Genero → Generos     Reservas → Boletos
    ↓
Pelicula_Actor → Actores              Clientes → Cliente_Membresia → Membresias
                                           ↓
                                        Ventas → Detalle_Venta → Productos
```

## 🎓 Requisitos para la Presentación

### Estructura de la Presentación (Evaluación)

Los estudiantes deberán realizar una presentación completa del proyecto explicando:

#### 1. Introducción (5 minutos)
- Descripción general del sistema
- Objetivos y alcance
- Contexto del negocio

#### 2. Diseño de la Base de Datos (15 minutos)

**Tablas** - Explicar cada una de las 20 tablas:
- Propósito y función
- Campos principales y tipos de datos
- Relaciones con otras tablas
- Ejemplo de datos

**Relaciones**:
- Diagrama ER completo
- Explicación de relaciones 1:N y M:N
- Integridad referencial

#### 3. Vistas (10 minutos)
- Explicar mínimo 5 vistas clave
- Propósito de cada vista
- Consultas que resuelven
- Casos de uso prácticos
- Demostración con resultados reales

#### 4. Stored Procedures (15 minutos)
- Explicar mínimo 5 procedimientos importantes
- Parámetros de entrada y salida
- Lógica de negocio implementada
- Demostración de ejecución
- Manejo de errores

#### 5. Triggers (10 minutos)
- Explicar mínimo 5 triggers críticos
- Eventos que los activan (BEFORE/AFTER INSERT/UPDATE/DELETE)
- Validaciones y reglas de negocio
- Ejemplos de funcionamiento
- Impacto en la integridad de datos

#### 6. Índices (5 minutos)
- Estrategia de indexación
- Índices más importantes
- Impacto en rendimiento
- Justificación de índices compuestos

#### 7. Consultas Avanzadas (10 minutos)
- Demostrar consultas complejas
- Uso de JOINs, subconsultas, agregaciones
- Consultas de reportes
- Optimización de consultas

#### 8. Casos de Uso (10 minutos)
- Flujo completo de reserva de boletos
- Proceso de venta de productos
- Generación de reportes
- Gestión de membresías

#### 9. Seguridad y Mantenimiento (5 minutos)
- Manejo de errores
- Validaciones implementadas
- Respaldos recomendados
- Consideraciones de seguridad

#### 10. Demo en Vivo (10 minutos)
- Ejecutar operaciones completas
- Mostrar triggers en acción
- Generar reportes
- Consultar vistas

### Criterios de Evaluación

| Criterio | Puntos |
|----------|--------|
| Claridad en explicación de tablas | 15% |
| Comprensión de stored procedures | 20% |
| Explicación de triggers y lógica de negocio | 20% |
| Demostración de vistas y consultas | 15% |
| Demo funcional del sistema | 15% |
| Calidad de la presentación visual | 10% |
| Manejo de preguntas | 5% |
| **Total** | **100%** |

### Materiales Requeridos para la Presentación

1. **Presentación PowerPoint/PDF** con:
   - Diagramas ER
   - Esquemas de tablas
   - Código de SP, triggers y vistas clave
   - Capturas de pantalla de resultados

2. **Demo en vivo** con:
   - Base de datos funcionando
   - Scripts preparados para ejecutar
   - Datos de prueba cargados

3. **Documentación impresa**:
   - Diccionario de datos
   - Lista completa de objetos (tablas, vistas, SP, triggers)
   - Manual de usuario básico

### Duración Total: 90-120 minutos

## 👥 Características Principales

### Gestión de Películas
- ✅ Clasificación por géneros
- ✅ Información de actores y director
- ✅ Clasificación por edades
- ✅ Control de estado (cartelera, próximamente)

### Gestión de Funciones
- ✅ Programación automática con validación de horarios
- ✅ Control de disponibilidad de asientos
- ✅ Múltiples tipos de sala (2D, 3D, IMAX, VIP, 4DX)
- ✅ Precios diferenciados

### Sistema de Reservas
- ✅ Reserva online con código único
- ✅ Generación automática de códigos QR
- ✅ Validación de edad según clasificación
- ✅ Expiración automática de reservas

### Programa de Fidelidad
- ✅ Acumulación automática de puntos
- ✅ Múltiples tipos de membresías
- ✅ Descuentos y beneficios
- ✅ Control de vigencia

### Punto de Venta
- ✅ Venta de productos de confitería
- ✅ Control de inventario
- ✅ Múltiples métodos de pago
- ✅ Cálculo automático de impuestos

## 📈 Reportes y Analíticas

- Dashboard ejecutivo con KPIs
- Top películas por período
- Ocupación de salas
- Análisis de ventas
- Productos más vendidos
- Clientes frecuentes y VIP
- Ingresos por complejo

## 🔒 Seguridad y Validaciones

- Validación de stock en ventas
- Validación de capacidad en reservas
- Prevención de conflictos de horarios
- Validación de edad para clasificaciones
- Protección contra eliminación de datos críticos
- Auditoría de cambios importantes

## 📝 Notas Importantes

- Los datos de ejemplo incluyen 20 registros por tabla
- Los precios incluyen cálculo automático de impuestos (16%)
- Los códigos QR y de reserva se generan automáticamente
- Las membresías se actualizan automáticamente al vencer

## 🤝 Contribuciones

Este proyecto es parte de un ejercicio académico para demostrar el diseño e implementación de una base de datos completa con:
- Diseño normalizado (3FN)
- Stored procedures
- Triggers para integridad
- Vistas para reportes
- Índices para optimización

## 📄 Licencia

Proyecto académico - Base de Datos

---

**Desarrollado como proyecto educativo de Base de Datos**
