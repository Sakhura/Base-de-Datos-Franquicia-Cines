Base de Datos - Franquicia de Cines (CineDB)
📋 Descripción del Proyecto
Sistema integral de gestión para una franquicia de cines que permite administrar la operación completa de complejos cinematográficos, incluyendo películas, funciones, reservas, ventas, clientes y empleados.
🎯 Objetivos

Gestionar múltiples complejos de cine en diferentes ciudades y países
Administrar cartelera de películas y programación de funciones
Controlar reservas y venta de boletos
Gestionar ventas de productos (confitería)
Implementar sistema de fidelización de clientes
Generar reportes y análisis de negocio

🗂️ Estructura de la Base de Datos
Tablas Principales (20 tablas)
#TablaDescripción1PaisesCatálogo de países2CiudadesCiudades donde operan los cines3ComplejosComplejos cinematográficos (multiplex)4SalasSalas de proyección por complejo5GenerosGéneros cinematográficos6ClasificacionesClasificaciones por edad7PeliculasCatálogo de películas8Pelicula_GeneroRelación películas-géneros (M:N)9ActoresCatálogo de actores10Pelicula_ActorRelación películas-actores (M:N)11FuncionesProgramación de funciones12ClientesRegistro de clientes13MembresiasTipos de membresías14Cliente_MembresiaMembresías activas de clientes15ReservasReservas de boletos16BoletosBoletos generados17ProductosCatálogo de productos (confitería)18VentasVentas de productos19Detalle_VentaDetalle de productos vendidos20EmpleadosPersonal de los complejos
🔧 Componentes del Sistema
📊 Vistas (20 vistas)

v_cartelera_completa - Películas en cartelera con información completa
v_funciones_hoy - Funciones programadas para hoy
v_peliculas_con_elenco - Películas con información del elenco
v_reservas_activas - Reservas confirmadas pendientes
v_top_peliculas_mes - Top 10 películas más vistas del mes
v_productos_disponibles - Catálogo de productos con stock
v_clientes_vip - Clientes con más puntos de fidelidad
v_ocupacion_salas - Estadísticas de ocupación por sala
v_ventas_diarias - Resumen de ventas diarias
v_productos_mas_vendidos - Ranking de productos
v_empleados_activos - Empleados activos por complejo
v_historial_funciones - Histórico de funciones realizadas
v_membresias_activas - Membresías vigentes
v_ingresos_complejo - Ingresos por complejo
v_proximos_estrenos - Películas próximas a estrenarse
v_boletos_pendientes - Boletos no utilizados
v_estadisticas_genero - Rendimiento por género
v_analisis_precios - Análisis de precios por tipo de sala
v_clientes_frecuentes - Clientes que más visitan
v_dashboard_ejecutivo - KPIs principales del negocio

⚙️ Stored Procedures (20 procedimientos)

sp_crear_reserva - Crear nueva reserva de boletos
sp_confirmar_reserva - Confirmar reserva y generar boletos
sp_cancelar_reserva - Cancelar reserva y liberar asientos
sp_buscar_funciones - Buscar funciones disponibles
sp_registrar_venta - Iniciar venta de productos
sp_agregar_producto_venta - Agregar producto a venta
sp_finalizar_venta - Completar venta y calcular totales
sp_peliculas_en_cartelera - Obtener cartelera actual
sp_reporte_ventas - Reporte de ventas por período
sp_top_peliculas - Top películas más vistas
sp_actualizar_puntos_cliente - Actualizar puntos de fidelidad
sp_verificar_disponibilidad_sala - Verificar disponibilidad de sala
sp_programar_funcion - Programar nueva función
sp_historial_cliente - Historial de reservas del cliente
sp_productos_mas_vendidos - Productos más vendidos
sp_ocupacion_salas - Ocupación de salas por complejo
sp_validar_boleto - Validar y usar boleto
sp_reporte_empleados - Reporte de empleados
sp_estadisticas_generales - Estadísticas generales
sp_buscar_peliculas - Búsqueda avanzada de películas

🔔 Triggers (25 triggers)

trg_validar_capacidad_reserva - Validar disponibilidad antes de reservar
trg_actualizar_asientos_reserva - Actualizar asientos al reservar
trg_restaurar_asientos_cancelacion - Restaurar asientos al cancelar
trg_validar_stock_venta - Validar stock antes de vender
trg_actualizar_stock_venta - Actualizar stock después de venta
trg_calcular_subtotal_detalle - Calcular subtotal automáticamente
trg_actualizar_total_venta - Actualizar total de venta
trg_agregar_puntos_fidelidad - Agregar puntos al completar reserva
trg_validar_fechas_membresia - Validar fechas de membresía
trg_actualizar_estado_membresia - Actualizar estado de membresía
trg_validar_horarios_funcion - Validar conflictos de horarios
trg_generar_codigo_reserva - Generar código único de reserva
trg_validar_edad_boleto - Validar edad según clasificación
trg_generar_qr_boleto - Generar código QR automático
trg_actualizar_estado_funcion - Actualizar estado según fecha
trg_validar_precio_funcion - Validar rangos de precio
trg_prevenir_eliminar_reserva - Prevenir eliminación de reservas
trg_auditoria_peliculas - Auditoría de cambios
trg_validar_capacidad_sala - Validar capacidad de sala
trg_calcular_expiracion_reserva - Calcular fecha de expiración
trg_validar_metodo_pago - Validar método de pago
trg_proteger_boletos_usados - Proteger boletos usados
trg_validar_descuento_membresia - Validar descuentos
trg_registrar_uso_boleto - Registrar hora de uso
trg_validar_duracion_pelicula - Validar duración

📑 Índices

Índices simples: Para optimizar búsquedas frecuentes
Índices compuestos: Para consultas complejas
Índices de claves foráneas: Para mejorar joins

🚀 Instalación
Requisitos Previos

MySQL 8.0 o superior
MySQL Workbench (recomendado)

Pasos de Instalación

Crear la base de datos y tablas

sqlSOURCE franquicia_cines.txt;

Insertar datos de prueba

sqlSOURCE Cine_db_inserts.txt;

Crear índices

sqlSOURCE indices.txt;

Crear vistas

sqlSOURCE vistas.txt;

Crear stored procedures

sqlSOURCE sp_cine.txt;

Crear triggers

sqlSOURCE trigger.txt;
📖 Uso del Sistema
Ejemplos de Consultas
Consultar cartelera actual
sqlSELECT * FROM v_cartelera_completa;
Crear una reserva
sqlCALL sp_crear_reserva(1, 5, 2, @id_reserva, @codigo);
SELECT @id_reserva, @codigo;
Ver top películas
sqlCALL sp_top_peliculas('2024-01-01', '2024-12-31');
Consultar ocupación de salas
sqlSELECT * FROM v_ocupacion_salas 
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
🎓 Requisitos para la Presentación
Estructura de la Presentación (Evaluación)
Los estudiantes deberán realizar una presentación completa del proyecto explicando:
1. Introducción (5 minutos)

Descripción general del sistema
Objetivos y alcance
Contexto del negocio

2. Diseño de la Base de Datos (15 minutos)
Tablas - Explicar cada una de las 20 tablas:

Propósito y función
Campos principales y tipos de datos
Relaciones con otras tablas
Ejemplo de datos

Relaciones:

Diagrama ER completo
Explicación de relaciones 1:N y M:N
Integridad referencial

3. Vistas (10 minutos)

Explicar mínimo 5 vistas clave
Propósito de cada vista
Consultas que resuelven
Casos de uso prácticos
Demostración con resultados reales

4. Stored Procedures (15 minutos)

Explicar mínimo 5 procedimientos importantes
Parámetros de entrada y salida
Lógica de negocio implementada
Demostración de ejecución
Manejo de errores

5. Triggers (10 minutos)

Explicar mínimo 5 triggers críticos
Eventos que los activan (BEFORE/AFTER INSERT/UPDATE/DELETE)
Validaciones y reglas de negocio
Ejemplos de funcionamiento
Impacto en la integridad de datos

6. Índices (5 minutos)

Estrategia de indexación
Índices más importantes
Impacto en rendimiento
Justificación de índices compuestos

7. Consultas Avanzadas (10 minutos)

Demostrar consultas complejas
Uso de JOINs, subconsultas, agregaciones
Consultas de reportes
Optimización de consultas

8. Casos de Uso (10 minutos)

Flujo completo de reserva de boletos
Proceso de venta de productos
Generación de reportes
Gestión de membresías

9. Seguridad y Mantenimiento (5 minutos)

Manejo de errores
Validaciones implementadas
Respaldos recomendados
Consideraciones de seguridad

10. Demo en Vivo (10 minutos)

Ejecutar operaciones completas
Mostrar triggers en acción
Generar reportes
Consultar vistas

Criterios de Evaluación
CriterioPuntosClaridad en explicación de tablas15%Comprensión de stored procedures20%Explicación de triggers y lógica de negocio20%Demostración de vistas y consultas15%Demo funcional del sistema15%Calidad de la presentación visual10%Manejo de preguntas5%Total100%
Materiales Requeridos para la Presentación

Presentación PowerPoint/PDF con:

Diagramas ER
Esquemas de tablas
Código de SP, triggers y vistas clave
Capturas de pantalla de resultados


Demo en vivo con:

Base de datos funcionando
Scripts preparados para ejecutar
Datos de prueba cargados


Documentación impresa:

Diccionario de datos
Lista completa de objetos (tablas, vistas, SP, triggers)
Manual de usuario básico



Duración Total: 90-120 minutos
👥 Características Principales
Gestión de Películas

✅ Clasificación por géneros
✅ Información de actores y director
✅ Clasificación por edades
✅ Control de estado (cartelera, próximamente)

Gestión de Funciones

✅ Programación automática con validación de horarios
✅ Control de disponibilidad de asientos
✅ Múltiples tipos de sala (2D, 3D, IMAX, VIP, 4DX)
✅ Precios diferenciados

Sistema de Reservas

✅ Reserva online con código único
✅ Generación automática de códigos QR
✅ Validación de edad según clasificación
✅ Expiración automática de reservas

Programa de Fidelidad

✅ Acumulación automática de puntos
✅ Múltiples tipos de membresías
✅ Descuentos y beneficios
✅ Control de vigencia

Punto de Venta

✅ Venta de productos de confitería
✅ Control de inventario
✅ Múltiples métodos de pago
✅ Cálculo automático de impuestos

📈 Reportes y Analíticas

Dashboard ejecutivo con KPIs
Top películas por período
Ocupación de salas
Análisis de ventas
Productos más vendidos
Clientes frecuentes y VIP
Ingresos por complejo

🔒 Seguridad y Validaciones

Validación de stock en ventas
Validación de capacidad en reservas
Prevención de conflictos de horarios
Validación de edad para clasificaciones
Protección contra eliminación de datos críticos
Auditoría de cambios importantes

📝 Notas Importantes

Los datos de ejemplo incluyen 20 registros por tabla
Los precios incluyen cálculo automático de impuestos (16%)
Los códigos QR y de reserva se generan automáticamente
Las membresías se actualizan automáticamente al vencer

🤝 Contribuciones
Este proyecto es parte de un ejercicio académico para demostrar el diseño e implementación de una base de datos completa con:

Diseño normalizado (3FN)
Stored procedures
Triggers para integridad
Vistas para reportes
Índices para optimización

📄 Licencia
Proyecto académico - Base de Datos

