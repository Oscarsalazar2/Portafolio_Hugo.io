---
title: "METEOR: Estación Meteorológica IoT"
stack: "IoT · Sensores · Dashboard"
tags: ["IoT", "Telemetría", "Dashboard"]
summary: "Sistema de sensores con envío de datos y visualización en web."
---

### Problema

Queríamos monitorear variables ambientales en tiempo real y conservar historial para comparar cambios por hora y por día, sin depender de mediciones manuales.

### Implementación

- Integración de sensores para captura de temperatura, humedad y otras métricas ambientales.
- Envío periódico de telemetría hacia un servicio de almacenamiento para consulta histórica.
- Dashboard web para visualización de tendencias, estados recientes y eventos relevantes.
- Registro de cambios administrativos para mantener trazabilidad.

### Decisiones técnicas

Priorizamos una arquitectura simple y modular: adquisición de datos, transporte y visualización como bloques separados. Eso permitió probar cada etapa por separado y detectar fallos más rápido.

### Reto que resolví

Durante pruebas hubo lecturas inestables por ruido y variaciones de conexión. Apliqué validaciones de rango y reglas básicas de limpieza para evitar que datos anómalos rompieran los gráficos.

### Qué sigue

Como siguiente paso, incorporaría alertas automáticas por umbrales y una capa de pronóstico básico para apoyar decisiones preventivas.
