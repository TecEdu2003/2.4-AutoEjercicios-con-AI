
## Instituto Tecnológico de Tijuana
    ## Depto de Sistemas y Computación
    ## Ing. En Sistemas Computacionales
    ## AutoEjercicios con AI
    ## Autor : Gallardo Dueñas Eduardo
    ## Repositorio: 2.4
    ## Fecha de revisión:   09/10/2023    
    ##   
     
```ARM
        .arch armv6
        .eabi_attribute 28, 1
        .eabi_attribute 20, 1
        .eabi_attribute 21, 1
        .eabi_attribute 23, 3
        .eabi_attribute 24, 1
        .eabi_attribute 25, 1
        .eabi_attribute 26, 2
        .eabi_attribute 30, 6
        .eabi_attribute 34, 1
        .eabi_attribute 18, 4
        .file   "Pi.c"
        .text
        .section        .rodata
        .align  2
.LC0:
        .ascii  "The value of pi is: %f\012\000"
        .text
        .align  2
        .global _printPi
        .arch armv6
        .syntax unified
        .arm
        .fpu vfp
        .type   _printPi, %function
_printPi:
        .fnstart
.LFB0:
        @ args = 0, pretend = 0, frame = 8
        @ frame_needed = 1, uses_anonymous_args = 0
        push    {fp, lr}
        .save {fp, lr}
        .setfp fp, sp, #4
        add     fp, sp, #4
        .pad #8
        sub     sp, sp, #8
        ldr     r2, .L2
        ldr     r3, .L2+4
        strd    r2, [fp, #-12]
        ldrd    r2, [fp, #-12]
        ldr     r0, .L2+8
        bl      printf
        nop
        sub     sp, fp, #4
        @ sp needed
        pop     {fp, pc}
.L3:
        .align  2
.L2:
        .word   1413754136
        .word   1074340347
        .word   .LC0
        .fnend
        .size   _printPi, .-_printPi
        .align  2
        .global main
        .syntax unified
        .arm
        .fpu vfp
        .type   main, %function
main:
        .fnstart
.LFB1:
        @ args = 0, pretend = 0, frame = 0
        @ frame_needed = 1, uses_anonymous_args = 0
        push    {fp, lr}
        .save {fp, lr}
        .setfp fp, sp, #4
        add     fp, sp, #4
        bl      _Z7printPiv
        mov     r3, #0
        mov     r0, r3
        pop     {fp, pc}
        .fnend
        .size   main, .-main
        .ident  "GCC: (Raspbian 8.3.0-6+rpi1) 8.3.0"
        .section        .note.GNU-stack,"",%progbits
/*
#include <stdio.h>  // Including the standard input-output header file for functions like printf.

/**
 * Prints the value of pi.
 */
/*
void printPi() {
    double pi = 3.14159265358979323846;  // The value of pi.
    printf("The value of pi is: %f\n", pi);
}

int main() {
    printPi();  // Calling the printPi function to print the value of pi.
    return 0;
}
*/

The value of pi is: 3.141593
