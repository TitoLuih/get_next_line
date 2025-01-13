# get_next_line

Este proyecto tiene como objetivo implementar una función llamada `get_next_line`, que lee una línea de un archivo o de la entrada estándar (stdin) de manera eficiente, devolviendo una línea completa cada vez que es llamada.

## Descripción

El proyecto **get_next_line** tiene como propósito desarrollar una función que lee una línea de un archivo de forma iterativa, gestionando el almacenamiento de datos entre invocaciones sucesivas de la función.

La función debe poder leer del archivo, de un buffer y devolver la línea solicitada. El reto principal es hacer que la función funcione correctamente, administrando la memoria de manera eficiente, y gestionando correctamente los saltos de línea.

### Función principal

```c
char *get_next_line(int fd);
```

- **Parámetros**: 
  - `fd`: el descriptor de archivo desde el cual se leerá. Puede ser un archivo o la entrada estándar.
  
- **Valor de retorno**:
  - Devuelve una línea leída del archivo (incluyendo el salto de línea `\n` si lo tiene).
  - Si no hay más líneas, devuelve `NULL`.
  
### Objetivos

1. Implementar la función `get_next_line` que lea una línea completa de un archivo.
2. Gestionar correctamente los buffers para asegurar que no se pierdan datos entre llamadas.
3. Implementar el manejo de memoria para que la función no cause fugas de memoria.
4. Garantizar que la función sea capaz de trabajar de manera eficiente con archivos grandes.

## Requisitos

- **Norma**: Se debe seguir la normativa del campus 42, que incluye reglas de estilo para el código y la gestión de archivos.

## Implementación

La implementación debe tomar en cuenta los siguientes puntos:

1. **Lectura del archivo**: La función debe leer los datos en trozos (bloques), almacenarlos en un buffer y luego extraer las líneas completas cuando sea necesario.
2. **Buffers**: Utilizar un buffer estático o dinámico para gestionar la lectura de datos, de manera que los datos previos se mantengan accesibles entre las llamadas a `get_next_line`.
3. **Memoria**: Asegurarse de que la memoria usada sea liberada correctamente cuando ya no sea necesaria.
4. **Líneas**: Cada vez que se invoca `get_next_line`, debe devolver una nueva línea hasta que no haya más datos que leer.

## Consideraciones

- Este proyecto es solo el comienzo de un aprendizaje en la manipulación eficiente de archivos y buffers en C.
- En este proyecto se debe tener cuidado con las fugas de memoria y la gestión correcta de los buffers para evitar errores.

