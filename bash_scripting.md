
Fase 1: Introducción y Navegación por el Sistema de Archivos

Antes de escribir scripts, hay que aprender a moverse por la terminal como si fuera nuestra casa.

    1.1 ¿Qué es la Terminal, la Shell y Bash?

        Relación entre el usuario, la interfaz de línea de comandos (CLI), la Shell y el sistema operativo (Kernel).

        Por qué Bash es el estándar en la mayoría de las distribuciones Linux y macOS.

    1.2 Comandos Esenciales de Navegación

        Dónde estoy parado: pwd.

        Listar el contenido de una carpeta: ls (y banderas clave como -l, -a, -h).

        Moverse entre directorios: cd (rutas absolutas vs. relativas, cd .., cd ~).

    1.3 Manipulación de Archivos y Carpetas

        Crear carpetas (mkdir) y archivos vacíos (touch).

        Copiar (cp), mover/renombrar (mv) y borrar (rm y el peligroso rm -rf).

    1.4 Visualización de Contenido

        Ver archivos pequeños: cat.

        Navegar por archivos grandes: less y more.

        Ver el principio o el final de un archivo: head y tail (y el súper útil tail -f para logs en tiempo real).

Fase 2: El Poder de las Tuberías y los Filtros

Aquí el estudiante aprende la filosofía Unix de "hacer una sola cosa y hacerla bien", conectando comandos pequeños para resolver problemas complejos.

    2.1 Canales Estándar de Entrada y Salida

        Entrada estándar (stdin), Salida estándar (stdout) y Error estándar (stderr).

    2.2 Redirecciones

        Guardar salidas en archivos (> y >>).

        Redirigir errores (2> o 2>&1).

        Usar archivos como entrada de un comando (<).

    2.3 Tuberías (Pipes: |)

        Cómo pasar la salida de un comando como entrada de otro de forma secuencial.

    2.4 Herramientas de Filtrado y Procesamiento

        Buscar texto en archivos (grep).

        Contar líneas, palabras o bytes (wc).

        Ordenar datos (sort) y eliminar duplicados (uniq).

        Extraer columnas de texto (cut).

Fase 3: Introducción al Scripting en Bash

El momento en el que dejamos de escribir comandos uno a uno y empezamos a agruparlos en archivos ejecutables.

    3.1 Tu Primer Script (hola_mundo.sh)

        La importancia del encabezado Shebang (#!/bin/bash).

        Guardar el script y darle permisos de ejecución (chmod +x script.sh).

        Cómo ejecutarlo correctamente (./script.sh).

    3.2 Variables y Tipos de Datos

        Declarar y usar variables (¡sin espacios alrededor del =!).

        Ámbito de las variables (locales vs. globales/entorno).

        Variables de entorno comunes ($PATH, $HOME, $USER).

    3.3 Captura de Datos de Entrada

        Interactuar con el usuario en tiempo real (read).

        Argumentos desde la línea de comandos ($1, $2, $@, $#).

    3.4 Sustitución de Comandos

        Guardar la salida de un comando dentro de una variable usando $(comando).

Fase 4: Estructuras de Control y Lógica

Aquí es donde Bash se convierte en un lenguaje de programación real que puede tomar decisiones y repetir tareas.

    4.1 Operadores de Comparación y Operaciones Matemáticas

        Evaluar números (con -eq, -ne, -gt, etc.).

        Evaluar cadenas de texto (==, !=).

        Evaluar archivos (¿existe el archivo?, ¿es un directorio? con -f, -d).

        Operaciones aritméticas básicas usando $(( operacion )).

    4.2 Condicionales (if, elif, else)

        Sintaxis rigurosa del if [ condicion ] (el espacio sagrado dentro de los corchetes).

        Estructuras de decisión múltiple (case).

    4.3 Bucles (Loops)

        Iterar sobre listas o rangos (for).

        Ejecutar mientras se cumpla una condición (while).

        Iterar sobre archivos en un directorio usando Wildcards (*.txt).

Fase 5: Bash Avanzado y Automatización Profesional

Para dominar por completo el entorno del sistema, procesar archivos de manera masiva y crear herramientas robustas.

    5.1 Funciones en Bash

        Cómo definir funciones, pasarles argumentos y retornar valores de estado.

    5.2 Manejo de Errores y Códigos de Salida

        Qué es el código de estado ($?) y por qué importa (éxito 0 vs. errores 1-255).

        Interrumpir el script inmediatamente si algo falla (set -e).

    5.3 Introducción a Expresiones Regulares (Regex) y Manipulación de Texto

        Modificar archivos de texto desde la terminal de forma masiva con sed.

        Procesamiento avanzado de datos tabulares con awk.

    5.4 Automatización del Sistema (Cron jobs)

        Cómo programar tu script de Bash para que se ejecute solo (diariamente, semanalmente, etc.) usando el servicio de cron.

