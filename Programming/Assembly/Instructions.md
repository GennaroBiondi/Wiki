# Intro
An instruction is a way to communicate with the CPU and make it do stuff.

# Instructions
## `mov`
the `mov` instruction copies data from an operand to another, the operand can be a register or a constant.
```
mov RAX, 5
mov [rsp], RAX
mov RBX, RAX
```
## `add`
the `add` instruction simply adds the first operand with the second and updates the first operand's value
```
; Assume RAX and RBX has data
add RAX, RBX
; Now RAX = RAX + RBX
```
## `sub`
the `sub` instruction subtracts the first operand with the second and updates the first operand's value
```
; Assume RAX and RBX has data
sub RAX, RBX
; Now RAX = RAX - RBX
```
## `imul`
the `imul` instruction multiplies the first operand with the second and updates the first operand's value

**NOTE**: this won't work with floating point numbers, hence the `i` in the name standing for "integer".
```
; Assume RAX and RBX has data
imul RAX, RBX
; Now RAX = RAX * RBX
```
## `push`
the `push` instruction accepts an operand, and subtracts from the `rsp` pointer the size of the operand in bytes.
```
; Assume RAX has data
push RAX
```
also this is the equivalent of `push`
```
sub rsp, 8 ; here we sub 8 because RAX is the size of 8 bytes, so a QWORD
mov [rsp], RAX
```
## `pop`
the `pop` instruction accepts an operand, and adds to the `rsp` pointer, updating the operand with the value that was in the stack
```
pop RAX
```
this is the equivalent of `pop`
```
mov RAX, [rsp]
add rsp, 8 ; here we add 8 because RAX is the size of 8 bytes, so a QWORD
```
## `inc`
the `inc` instruction accepts an operand, and increments it by one.

```
inc RAX
```
this is the equivalent of `inc`
```
add RAX, 1
```
## `dec`
the `dec` instruction accepts an operand, and decrements it by one.

```
dec RAX
```
this is the equivalent of `inc`
```
sub RAX, 1
```