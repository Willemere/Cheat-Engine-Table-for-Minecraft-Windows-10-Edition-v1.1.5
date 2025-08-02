# Cheat-Engine-Table-for-Minecraft-Windows-10-Edition-v1.1.5
## Possible problems:
Table created for **Minecraft: Windows 10 Edition V1.1.5**
## For start:
Download [Cheat Engine](https://github.com/cheat-engine/cheat-engine) -> Run File

## Nobody will need (Minecraft: Windows 10 Editon v0.15.10):

- Fast Eat
```Lua
[ENABLE]

aobscanmodule(INJECT,Minecraft.Win10.DX11.exe,8B 83 78 0F 00 00 EB 05 48 8B CB FF D2 66) // should be unique
alloc(newmem,$1000,INJECT)

label(code)
label(return)

newmem:

code:
  mov [rbx+00000F78],1
  jmp return

INJECT:
  jmp newmem
  nop
return:
registersymbol(INJECT)

[DISABLE]

INJECT:
  db 8B 83 78 0F 00 00

unregistersymbol(INJECT)
dealloc(newmem)
```
- Reach static adress
```Lua
  Minecraft.Win10.DX11.exe+B52A70
```
- HitBox
``` Lua
[ENABLE]

aobscanmodule(INJECT,Minecraft.Win10.DX11.exe,F3 0F 10 81 D0 00 00 00 C3) // should be unique
alloc(newmem,$1000,INJECT)

label(code)
label(return)

newmem:

code:
  mov [rcx+000000D0],(float)8
  jmp return

INJECT:
  jmp newmem
  nop 3
return:

registersymbol(INJECT)

[DISABLE]

INJECT:
  db F3 0F 10 81 D0 00 00 00

unregistersymbol(INJECT)
dealloc(newmem)
```

