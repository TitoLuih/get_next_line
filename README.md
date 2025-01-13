get_next_line

Este proyecto tiene como objetivo implementar una función llamada get_next_line, que lee una línea de un archivo o de la entrada estándar (stdin) de manera eficiente, devolviendo una línea completa cada vez que es llamada.
Descripción

El proyecto get_next_line tiene como propósito desarrollar una función que lee una línea de un archivo de forma iterativa, gestionando el almacenamiento de datos entre invocaciones sucesivas de la función.

La función debe poder leer del archivo, de un buffer y devolver la línea solicitada. El reto principal es hacer que la función funcione correctamente, administrando la memoria de manera eficiente, y gestionando correctamente los saltos de línea.
Función principal

char *get_next_line(int fd);

    Parámetros:
        fd: el descriptor de archivo desde el cual se leerá. Puede ser un archivo o la entrada estándar.
    Valor de retorno:
        Devuelve una línea leída del archivo (incluyendo el salto de línea \n si lo tiene).
        Si no hay más líneas, devuelve NULL.

Objetivos

    Implementar la función get_next_line que lea una línea completa de un archivo.
    Gestionar correctamente los buffers para asegurar que no se pierdan datos entre llamadas.
    Implementar el manejo de memoria para que la función no cause fugas de memoria.
    Garantizar que la función sea capaz de trabajar de manera eficiente con archivos grandes.

Requisitos

    C89: El proyecto debe ser implementado utilizando el estándar C89.
    Norma: Se debe seguir la normativa del campus 42, que incluye reglas de estilo para el código y la gestión de archivos.

Implementación

La implementación debe tomar en cuenta los siguientes puntos:

    Lectura del archivo: La función debe leer los datos en trozos (bloques), almacenarlos en un buffer y luego extraer las líneas completas cuando sea necesario.
    Buffers: Utilizar un buffer estático o dinámico para gestionar la lectura de datos, de manera que los datos previos se mantengan accesibles entre las llamadas a get_next_line.
    Memoria: Asegurarse de que la memoria usada sea liberada correctamente cuando ya no sea necesaria.
    Líneas: Cada vez que se invoca get_next_line, debe devolver una nueva línea hasta que no haya más datos que leer.

Cómo usar

    Crear un archivo de código fuente, por ejemplo main.c, donde llames a la función get_next_line.
    Compilar el proyecto con un compilador compatible con C89.
    Ejecutar el archivo y ver cómo se leen las líneas del archivo indicado.

Ejemplo de uso:

#include "get_next_line.h"

int main(void)
{
    int fd = open("archivo.txt", O_RDONLY);
    char *line;

    while ((line = get_next_line(fd)) != NULL)
    {
        printf("%s", line);
        free(line);
    }
    close(fd);
    return (0);
}

En este ejemplo, la función get_next_line lee línea por línea desde el archivo archivo.txt y las imprime en pantalla.
Compilación

Para compilar el proyecto, utiliza el siguiente comando:

gcc -Wall -Wextra -Werror -o get_next_line main.c get_next_line.c

Asegúrate de incluir los archivos get_next_line.c y get_next_line.h en tu proyecto.
Consideraciones

    Este proyecto es solo el comienzo de un aprendizaje en la manipulación eficiente de archivos y buffers en C.
    En este proyecto se debe tener cuidado con las fugas de memoria y la gestión correcta de los buffers para evitar errores.

Autores

    [Tu nombre o tu alias de 42]
