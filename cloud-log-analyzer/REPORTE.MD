Práctica 4.2

Implementación de un Mini Cloud Log Analyzer en ARM64

Nombre: Allyson
Curso: Arquitectura de Computadoras / Ensamblador ARM64
Fecha: Abril 2026

---

🧠 Introducción

En los sistemas modernos de cómputo en la nube, los registros (logs) son fundamentales para monitorear el estado de los servicios, detectar fallas y analizar el comportamiento del sistema.

En esta práctica se desarrolló un analizador de logs simplificado utilizando lenguaje ensamblador ARM64, el cual procesa códigos de estado HTTP y los clasifica en diferentes categorías.

---

🎯 Objetivo general

Diseñar e implementar un programa en ensamblador ARM64 que procese registros de eventos desde la entrada estándar (stdin) y clasifique los códigos HTTP en distintas categorías.

---

🎯 Objetivos específicos

- Aplicar programación en ensamblador ARM64 bajo Linux
- Manejar registros y memoria
- Implementar estructuras iterativas
- Utilizar instrucciones de comparación
- Emplear saltos condicionales
- Usar syscalls de Linux
- Compilar mediante GNU Make
- Trabajar con control de versiones

---

⚙️ Descripción del programa

El programa desarrollado:

1. Lee códigos HTTP desde la entrada estándar
2. Procesa cada número carácter por carácter
3. Convierte los datos de texto a valores numéricos
4. Clasifica los códigos en:
   - 2xx: respuestas exitosas
   - 4xx: errores del cliente
   - 5xx: errores del servidor
5. Muestra un reporte final con los resultados

---

🔄 Funcionamiento

El flujo del programa es el siguiente:

1. Se inicializan los contadores en cero
2. Se lee la entrada mediante la syscall "read"
3. Se analiza cada carácter:
   - Si es un dígito, se acumula el número
   - Si es un salto de línea, se clasifica el número
4. Se repite hasta terminar la entrada
5. Se imprime el resultado con "write"

---

💻 Ejemplo de ejecución

Entrada:

200
404
500
201
503

Salida:

=== Mini Cloud Log Analyzer ===
Éxitos 2xx: 2
Errores 4xx: 1
Errores 5xx: 2

---

🧩 Tecnologías utilizadas

- Lenguaje ensamblador ARM64
- Bash
- GNU Make
- Syscalls de Linux

---

⚠️ Problemas encontrados

Durante el desarrollo se presentaron algunos inconvenientes:

- Error de compilación por uso de linker no disponible
- Diferencia de arquitectura (x86 vs ARM64)
- Problemas de ejecución por formato incompatible
- Ubicación incorrecta de archivos dentro del repositorio

---

✅ Soluciones aplicadas

- Modificación del Makefile para usar linker compatible
- Uso de entorno adecuado en AWS
- Identificación correcta de rutas de archivos
- Uso de herramientas como "qemu" (cuando fue necesario)

---

🏁 Conclusión

Esta práctica permitió comprender el funcionamiento de un programa en ensamblador ARM64 aplicado a un problema real como el análisis de logs.

Se reforzaron conceptos clave como el manejo de memoria, estructuras de control, syscalls y procesamiento de datos. Además, se adquirió experiencia en el uso de entornos en la nube y herramientas de desarrollo en Linux.

---

📌 Observaciones

El programa puede extenderse para incluir:

- Manejo de códigos inválidos
- Cálculo de porcentajes
- Soporte para más categorías

---
