---
title: "Generador y verificador de contraseñas"
stack: "HTML · CSS · JavaScript · Bootstrap · zxcvbn"
tags: ["Seguridad", "Frontend", "Validación"]
summary: "Aplicación web que genera contraseñas personalizadas, evalúa su fortaleza y verifica si han sido comprometidas en filtraciones públicas."
---

### Problema

Necesitaba una herramienta práctica para crear contraseñas más seguras y, al mismo tiempo, validar si una contraseña ya fue expuesta en internet. La idea era resolverlo desde una interfaz sencilla, sin instalar software adicional.

### Lo que construí

Generador de contraseñas configurables por longitud y tipo de caracteres (letras, números y símbolos).
Copia automática al portapapeles con confirmación visual para agilizar el uso.
Verificador de fortaleza con barra de progreso y retroalimentación clara usando zxcvbn.
Comprobación de contraseñas comprometidas mediante consulta segura a la API de Have I Been Pwned (modelo k-anonymity).
Decisiones técnicas
Separé la lógica de generación, evaluación y validación para que el mantenimiento fuera más simple. También prioricé mensajes comprensibles para el usuario final, incluyendo traducción de sugerencias técnicas a español y niveles de seguridad fáciles de interpretar.

### Reto que resolví
Uno de los retos fue equilibrar experiencia de usuario y seguridad: no solo mostrar una puntuación, sino explicar por qué una contraseña era débil y detectar casos donde parecía fuerte, pero ya había sido filtrada.

### Qué mejoraría hoy
Agregaría validaciones extra de entrada (rangos y estados límite), historial local de contraseñas generadas y una suite de pruebas automáticas para cubrir escenarios de fortaleza, traducciones y disponibilidad de API.
