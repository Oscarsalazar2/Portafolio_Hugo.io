---
title: "eCartilla de Vacunación Digital"
stack: "Laravel · React · PostgreSQL"
tags: ["QR", "Roles", "Notificaciones", "PDF"]
summary: "Plataforma para registrar y verificar vacunas con QR, roles y exportaciones."
---

### Contexto

Este proyecto nació como una propuesta para digitalizar el seguimiento de esquemas de vacunación y evitar pérdida de información en registros físicos. Se trabajó con enfoque de trazabilidad y consulta rápida.

### Qué desarrollé

- Módulo de autenticación y control de roles (administración, personal médico y captura).
- Generación de códigos QR para validar registros de forma inmediata.
- API y base de datos PostgreSQL para historial de vacunas, refuerzos y consultas por usuario.
- Vistas en React para dashboard, búsqueda de pacientes y exportación en PDF.

### Decisiones técnicas

Usé Laravel para acelerar la capa de negocio y asegurar una API ordenada con validaciones consistentes. En frontend, React permitió dividir pantallas por componentes y reutilizar lógica de formularios.

### Reto que resolví

El reto principal fue mantener consistencia entre estados del historial (aplicada, pendiente, refuerzo) sin duplicar información. Ajusté el modelo de datos y reglas de negocio para que cada actualización quedara auditada y fuera fácil de consultar.

### Resultado y aprendizaje

El proyecto quedó como una base funcional para pruebas internas, con flujo completo de registro a verificación. Me dejó experiencia fuerte en diseño de APIs, control de acceso por roles y decisiones de UX en sistemas administrativos.
