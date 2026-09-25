# Intro
the `x86_64` architecture provides registers. Registers are a place to store values depending on their size, usually registers are big enough to fit a `QWORD`, but some registers can be smaller, or even a smaller part of one.

Every register has a convention depending on the `ABI` of the program.
in this document i'll use the convention of the `System V Linux ABI`

## Register Views
some registers are special, as they hold the value of a bigger one.

a register can be composed of smaller registers, that can be composed of smaller ones.

For instance, here's the tree of the `RAX` Register, and their respective sizes

`RAX`  = `QWORD`
 └── `EAX` = `DWORD`
      └── `AX` = `WORD`
           ├── `AH` = `BYTE`
           └── `AL` = `BYTE`

for a better illustration of the actual memory layout:

| `RAX` | `RAX` | `RAX` | `RAX` | `EAX` | `EAX` | `AX (AH)` | `AX (AL)` |
| ----- | ----- | ----- | ----- | ----- | ----- | --------- | --------- |
as you can see, the `EAX` Register is a view onto the lower 4 bytes of `RAX`, in the same way, `AX` is a view onto the lower 2 bytes of `EAX`, and `AH` is a view onto the higher byte of `AX`, while `AL` on the lower byte
# General Purpose Registers
A General Purpose register (which will be abbreviated in `GPR`), is a register which by convention can be used for generally anything, hence the name. They're also called `scratch` registers.

Here are the General Purpose Registers and the registers that hold a smaller view of them:

`RAX = QWORD`
 `└── EAX = DWORD`
      `└── AX = WORD`
           `├── AH = BYTE`
           `└── AL = BYTE`

`RBX = QWORD`
 `└── EBX = DWORD`
      `└── BX = WORD`
           `├── BH = BYTE`
           `└── BL = BYTE`

`RCX = QWORD`
 `└── ECX = DWORD`
      `└── CX = WORD`
           `├── CH = BYTE`
           `└── CL = BYTE`

`RDX = QWORD`
 `└── EDX = DWORD`
      `└── DX = WORD`
           `├── DH = BYTE`
           `└── DL = BYTE`

`RSI = QWORD`
 `└── ESI = DWORD`
      `└── SI = WORD`
           `└── SIL = BYTE`

`RDI = QWORD`
 `└── EDI = DWORD`
      `└── DI = WORD`
           `└── DIL = BYTE`

`RBP = QWORD`
 `└── EBP = DWORD`
      `└── BP = WORD`
           `└── BPL = BYTE`

`RSP = QWORD`
 `└── ESP = DWORD`
      `└── SP = WORD`
           `└── SPL = BYTE`

`R8 = QWORD`
 `└── R8D = DWORD`
      `└── R8W = WORD`
           `└── R8B = BYTE`

`R9 = QWORD`
 `└── R9D = DWORD`
      `└── R9W = WORD`
           `└── R9B = BYTE`

`R10 = QWORD`
 `└── R10D = DWORD`
      `└── R10W = WORD`
           `└── R10B = BYTE`

`R11 = QWORD`
 `└── R11D = DWORD`
      `└── R11W = WORD`
           `└── R11B = BYTE`

`R12 = QWORD`
 `└── R12D = DWORD`
      `└── R12W = WORD`
           `└── R12B = BYTE`

`R13 = QWORD`
 `└── R13D = DWORD`
      `└── R13W = WORD`
           `└── R13B = BYTE`

`R14 = QWORD`
 `└── R14D = DWORD`
      `└── R14W = WORD`
           `└── R14B = BYTE`

`R15 = QWORD`
 `└── R15D = DWORD`
      `└── R15W = WORD`
           `└── R15B = BYTE`

## `ABI` Conventions
although `GPR`s are called "General Purpose", `ABI`s usually create conventions for them, following the `System V Linux ABI`, here is how each `GPR` should be used:

| *Register* | *Purpose*                           |
| ---------- | ----------------------------------- |
| `RAX`      | Used as a return value for routines |
| `RBX`      | callee-saved                        |
| `RDI`      | First argument                      |
| `RSI`      | Second argument                     |
| `RDX`      | Third argument                      |
| `RCX`      | Fourth argument                     |
| `R8`       | Fifth argument                      |
| `R9`       | Sixth argument                      |
| `RBP`      | Frame pointer, callee-saved         |
| `R10`      | caller-saved                        |
| `R11`      | caller-saved                        |
| `R12`      | callee-saved                        |
| `R13`      | callee-saved                        |
| `R14`      | callee-saved                        |
| `R15`      | callee-saved                        |
