---
title: "Control Hijacking"
date: 2022-11-01T00:09:30-04:00
description: "Hijack a built computer program"
draft: true
---

# Basic Knowledge
## Registers 
### General Purpose Registers
- EAX: Used to store return values
- EBX
- ECX
- EDX
- ESI

### Special Purpose Registers
- EIP: Instruction Pointer
- ESP: Stack Pointer, indicate the top of the function 
- EBP: Frame / Base Pointer, indicate the bottom of the function

## CPU Instructions (Intel Syntax)

- Move a value to a register: `mov eax, 0x34`
- Add a value to a register: `add eax 10`
- Jump to a line of code: `jmp 0x123`
- Call a function (returns to the next line): `call 0x1234`

## Stack
```x86
push    0x0a
push    0x6c
push    0xff
pop     eax
pop     eax
```

Note that the `pop` does not eliminate the value of the stack. The value will remain but the stack pointer will move.
