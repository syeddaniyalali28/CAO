# CAO
.data
line1: .asciiz "ENTER NUMBER OF DISC "
part1: .asciiz "\nMOVE DISC "
part2: .asciiz " FROM ROD "
part3: .asciiz " TO ROD "
 
.text
.globl main
main:
    li $v0,  4          # print string
    la $a0,line1
    syscall
    li $v0,  5          # read integer
    syscall
 
    # parameters for the routine
    add $a0, $v0, $zero # move to $a0
    li $a1, 'A'
    li $a2, 'B'
    li $a3, 'C'
 
    jal hanoi           # call hanoi routine
 
    li $v0, 10          # exit
    syscall
