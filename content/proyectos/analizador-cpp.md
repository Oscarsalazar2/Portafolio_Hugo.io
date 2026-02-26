---
title: "Analizador Léxico/Sintáctico para C++"
stack: "Java · JFlex · CUP"
tags: ["Compiladores", "Tokens", "Parser"]
summary: "Analizador que tokeniza y parsea estructuras comunes de C++."
---

### Problema

En la materia de compiladores necesitábamos pasar de teoría a algo funcional: recibir código estilo C++, identificar tokens y validar la estructura sintáctica sin depender de herramientas externas de IDE.

### Lo que construí

- Analizador léxico con JFlex para reconocer identificadores, palabras reservadas, operadores y literales.
- Analizador sintáctico con CUP para validar estructuras como condicionales, ciclos y declaraciones de funciones.
- Base para reporte de errores por línea/columna y preparación de un árbol sintáctico para futuras etapas.

### Decisiones técnicas

Elegí separar reglas léxicas y sintácticas desde el inicio para poder depurar más rápido. También prioricé mensajes de error legibles, porque en pruebas nos dimos cuenta de que detectar el fallo no servía si no se entendía dónde ocurrió.

### Reto que resolví

Uno de los errores más frecuentes era la ambigüedad en ciertas producciones de la gramática. Ajusté precedencias y reorganicé reglas para reducir conflictos y evitar falsos positivos al parsear expresiones.

### Qué mejoraría hoy

Agregaría una suite de pruebas automáticas con casos válidos e inválidos, y un módulo visual para mostrar el árbol sintáctico de forma interactiva.
