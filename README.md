
## Instituto Tecnológico de Tijuana
    ## Depto de Sistemas y Computación
    ## Ing. En Sistemas Computacionales
    ## AutoEjercicios con AI
    ## Autor : Gallardo Dueñas Eduardo
    ## Repositorio: 2.4
    ## Fecha de revisión:   09/10/2023    
    ##   
     
```C++


#include <stdio.h>  // Including the standard input-output header file for functions like printf.

/**
 * Prints the value of pi.
 */

void printPi() {
    double pi = 3.14159265358979323846;  // The value of pi.
    printf("The value of pi is: %f\n", pi);
}

int main() {
    printPi();  // Calling the printPi function to print the value of pi.
    return 0;
}


The value of pi is: 3.141593


/*
@ Definición de la arquitectura ARMv6
.arch armv6

@ Configuración del EABI (Embedded Application Binary Interface)
.eabi_attribute 28, 1   @ Compatibilidad con el EABI
.eabi_attribute 20, 1   @ Uso de registro de punto flotante simple (VFP)
.eabi_attribute 21, 1   @ Opción de depuración avanzada
.eabi_attribute 23, 3   @ Convención de llamada ARM y registro VFP
.eabi_attribute 24, 1   @ ABI duro (hard ABI)
.eabi_attribute 25, 1   @ Compatibilidad con punto flotante de doble precisión (VFP)
.eabi_attribute 26, 2   @ Convención de llamada ARM para punto flotante (soft-float)
.eabi_attribute 30, 6   @ Tamaño de int y alineación
.eabi_attribute 34, 1   @ Enumeraciones enteras
.eabi_attribute 18, 4   @ Tamaño de puntero

@ Nombre del archivo fuente
.file "Pi.c"

@ Sección de solo lectura para datos constantes
.section .rodata
.align 2
.LC0:
.ascii "El valor de pi es: %f\012\000"

@ Declaración de la función _printPi
.text
.align 2
.global _printPi

@ Comienza la función _printPi
_printPi:
.fnstart
.LFB0:

@ Inicializa el marco de la función
push {fp, lr}
.save {fp, lr}
.setfp fp, sp, #4
add fp, sp, #4

@ Reserva espacio en la pila
sub sp, sp, #8

@ Carga la dirección de la cadena .LC0 en los registros r2 y r3
ldr r2, .L2
ldr r3, .L2+4

@ Almacena los valores en la pila
strd r2, [fp, #-12]
ldrd r2, [fp, #-12]

@ Carga la dirección de la cadena .LC0 en r0
ldr r0, .L2+8

@ Llama a la función printf
bl printf
nop

@ Restaura el marco de la pila
sub sp, fp, #4

@ Retorna
pop {fp, pc}
.L3:
.align 2
.L2:
.word 1413754136
.word 1074340347
.word .LC0
.fnend
.size _printPi, .-_printPi

@ Declaración de la función principal
.align 2
.global main

@ Comienza la función principal
main:
.fnstart
.LFB1:

@ Llama a la función _printPi
bl _printPi

@ Retorna 0
mov r3, #0
mov r0, r3

@ Retorna desde la función main
pop {fp, pc}
.fnend
.size main, .-main

@ Información sobre el compilador
.ident "GCC: (Raspbian 8.3.0-6+rpi1) 8.3.0"

@ Nota sobre la pila de ejecución
.section .note.GNU-stack, "", %progbits
*/
