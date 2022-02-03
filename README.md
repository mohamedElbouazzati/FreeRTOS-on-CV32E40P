# FreeRTOS-on-CV32E40P-RISC-V-Processor
### FreeRTOS Using Spike:
 ```
  git clone https://github.com/FreeRTOS/FreeRTOS.git
  cd FreeRTOS/FreeRTOS/Demo/RISC-V-spike-htif_GCC
  make
  spike -p1 --isa RV32IMA -m0x80000000:0x10000000 --rbb-port 9824 ./build/RTOSDemo32.axf
  openocd -f spike-1.cfg  # for debugging
  riscv32-unknown-elf-gdb build/RTOSDemo32.axf  # for debugging
  ```
  #### Results :
  
  ```
  Listening for remote bitbang connection on port 9824.
Hello FreeRTOS!
^C: help
Interactive commands:
reg <core> [reg]                # Display [reg] (all if omitted) in <core>
freg <core> <reg>               # Display float <reg> in <core> as hex
fregh <core> <reg>              # Display half precision <reg> in <core>
fregs <core> <reg>              # Display single precision <reg> in <core>
fregd <core> <reg>              # Display double precision <reg> in <core>
vreg <core> [reg]               # Display vector [reg] (all if omitted) in <core>
pc <core>                       # Show current PC in <core>
mem <hex addr>                  # Show contents of physical memory
str <core> <hex addr>           # Show NUL-terminated C string at <hex addr> in core <core>
until reg <core> <reg> <val>    # Stop when <reg> in <core> hits <val>
until pc <core> <val>           # Stop when PC in <core> hits <val>
untiln pc <core> <val>          # Run noisy and stop when PC in <core> hits <val>
until mem <addr> <val>          # Stop when memory <addr> becomes <val>
while reg <core> <reg> <val>    # Run while <reg> in <core> is <val>
while pc <core> <val>           # Run while PC in <core> is <val>
while mem <addr> <val>          # Run while memory <addr> is <val>
run [count]                     # Resume noisy execution (until CTRL+C, or [count] insns)
r [count]                         Alias for run
rs [count]                      # Resume silent execution (until CTRL+C, or [count] insns)
quit                            # End the simulation
q                                 Alias for quit
help                            # This screen!
h                                 Alias for help
Note: Hitting enter is the same as: run 1
  ```
 #### Registers :
 ```
  : reg 0 
zero: 0x00000000  ra: 0x80000ea8  sp: 0x8008ffec  gp: 0x800808f0
  tp: 0x00000000  t0: 0x00000000  t1: 0x00000000  t2: 0x00000000
  s0: 0x80081390  s1: 0x00000002  a0: 0x80081390  a1: 0x00000000
  a2: 0x00000054  a3: 0x80080178  a4: 0x00000000  a5: 0xaaaaaaaa
  a6: 0x00000000  a7: 0x00000000  s2: 0x00001000  s3: 0x80080380
  s4: 0x00000000  s5: 0x8000011c  s6: 0x00000000  s7: 0x80002dbc
  s8: 0x00000000  s9: 0x00000000 s10: 0x00000000 s11: 0x00000000
  t3: 0x00000000  t4: 0x00000000  t5: 0x00000000  t6: 0x00000000
``` 
### References:
  * **Get started with FreeRTOS** : https://www.freertos.org/FreeRTOS-quick-start-guide.html
  * **RISCV DEMO :** https://www.freertos.org/Using-FreeRTOS-on-RISC-V.html
  * **Board RISCV :** https://www.freertos.org/RTOS-RISC-V-Vegaboard_Pulp.html
  * **Using SPIKE ISA SIMULATOR** : https://interactive.freertos.org/hc/en-us/community/posts/210030246-32-bit-and-64-bit-RISC-V-using-GCC
  * **Using QEMU** : https://www.freertos.org/RTOS-RISC-V-FreedomStudio-QMEU.html
  * **Supported Boards :** https://www.freertos.org/a00090.html
