# Issue 1.3 – Diferencia entre Editor e IDE

## ¿Qué es un editor de código?

Un editor de código es una herramienta que permite escribir y editar código fuente.
Su función principal es facilitar la escritura de programas mediante resaltado de sintaxis,
autocompletado y gestión básica de archivos.

Un editor por sí mismo no incluye todas las herramientas necesarias para desarrollar software
completo, como compiladores, depuradores o gestores de dependencias.

## ¿Qué es un IDE?

Un IDE (Integrated Development Environment) es un entorno de desarrollo completo que integra
varias herramientas necesarias para programar en una sola aplicación.

Un IDE normalmente incluye:

- Editor de código
- Compilador o intérprete
- Depurador (debugger)
- Gestión de dependencias
- Integración con control de versiones
- Herramientas de análisis de código

Ejemplos de IDE conocidos incluyen IntelliJ IDEA, Eclipse o Visual Studio.

## ¿Por qué VS Code puede funcionar como IDE?

Visual Studio Code es originalmente un editor de código, pero gracias a su sistema de
extensiones puede ampliarse para incluir muchas funcionalidades de un IDE.

Por ejemplo, en este proyecto se han instalado herramientas como:

- ESLint para análisis de código
- Prettier para formateo automático
- Node.js y npm para gestión del proyecto

Gracias a estas extensiones y herramientas, Visual Studio Code puede proporcionar un
entorno de desarrollo completo similar al de un IDE.

## Conclusión

Aunque Visual Studio Code es técnicamente un editor de código, su arquitectura basada
en extensiones permite transformarlo en un entorno de desarrollo completo adaptado
a diferentes lenguajes y necesidades del desarrollador.

Para analizar el rendimiento de la página se utilizó la pestaña **Network** de las herramientas de desarrollo del navegador.

Se recargó la página y se analizaron las peticiones realizadas por el navegador, observando el tipo de recurso, tamaño y tiempo de carga de cada uno.

El análisis permitió identificar algunos posibles problemas de rendimiento.

### Problemas detectados

1. **Archivo JavaScript de gran tamaño**
   - Recurso: `main.tsx-b1444874.js`
   - Tipo: script
   - Tamaño: 584 KB

   **Problema:**  
   Un archivo JavaScript grande puede ralentizar la carga de la página.

   **Solución propuesta:**  
   Minificar el código o dividir el archivo en varios bundles (code splitting).

---

2. **Recurso que falla al cargarse**
   - Recurso: `invalid`
   - Estado: failed
   - Tipo: script

   **Problema:**  
   El navegador intenta cargar un script que no existe o cuya ruta es incorrecta.

   **Solución propuesta:**  
   Revisar la ruta del archivo o verificar que el recurso exista en el servidor.

---

3. **Número elevado de peticiones**
   - Total de peticiones: 61

   **Problema:**  
    Un número alto de peticiones puede aumentar el tiempo total de carga.

   **Solución propuesta:**  
    Combinar archivos, usar caché o utilizar una CDN.

   ### Captura del análisis de Network

   ![Network Analysis](img/network-analysis.jpg)
