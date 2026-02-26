---
title: "Mapeo Solar Inteligente para Invernadero"
stack: "React · Vite · Tailwind CSS · Fastify · PostgreSQL · Chart.js · Leaflet · Zod · WebSocket · ESP32/Arduino"
tags: ["IoT", "Monitoreo", "Visualización de datos", "Tiempo real"]
summary: "Plataforma web para monitorear luminosidad por sensores en un invernadero, visualizar mapas de calor y generar reportes por día/semana/mes para apoyar decisiones de ubicación de plantas."
---

### Problema

Necesitaba centralizar las lecturas de varios sensores de luz en un solo panel para ver, en tiempo real, qué zonas del invernadero recibían menos iluminación. El objetivo era convertir datos crudos (lux) en información útil para decidir reubicaciones de plantas y mejorar el aprovechamiento de luz solar.

### Lo que construí

Dashboard en React con actualización en vivo del estado de sensores y control de ejecución (en vivo/pausado).  
Mapa de calor por cuadrícula (3x3) con codificación visual de intensidad de luz y recomendaciones de reubicación según zonas con menor captación.  
Gráficas por sensor y gráfica general con series temporales, filtros por rango horario y agrupación de lecturas para facilitar análisis.  
Módulo de reportes agregados por día, semana y mes con métricas promedio, máximas y mínimas.  
Backend en Fastify con endpoints REST para `heatmap`, `series`, `reports` y recepción de lotes de lecturas desde ESP32/Arduino.  
Persistencia en PostgreSQL con esquema para sensores, lecturas, calibración y alertas, más consultas optimizadas para últimos datos y agregaciones por ventana de tiempo.

### Decisiones técnicas

Separé frontend y backend para mantener una arquitectura clara y escalable. En API usé validación con Zod para asegurar entradas consistentes (parámetros y lotes de lecturas) y evitar errores silenciosos. En frontend prioricé rendimiento y UX con debounce, abort de peticiones, reintentos y caché temporal para evitar sobrecarga y estados inestables. También incorporé modo demo para pruebas sin hardware conectado.

### Reto que resolví

Uno de los retos fue balancear actualización en tiempo real con estabilidad de interfaz: había que refrescar datos frecuentemente sin generar condiciones de carrera ni bloquear la experiencia del usuario. Se resolvió controlando concurrencia de peticiones, manejo de abortos y agregación inteligente de datos para visualización.

### Qué mejoraría hoy

Añadiría autenticación por roles y trazabilidad de cambios de calibración por sensor.  
Implementaría alertas automáticas (umbrales configurables) por correo/WhatsApp/Telegram.  
Crearía pruebas automáticas de API y componentes críticos del dashboard.  
Sumaría pronóstico de luminosidad y recomendaciones predictivas con modelos simples de series de tiempo.
