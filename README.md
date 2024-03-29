## Find instructions for RISC-V alphanumeric/ascii shellcode

### requirements
[Spike simulator](https://github.com/riscv/riscv-isa-sim.git)

### how to use
Before you compile, you need to clone and compile [Spike simulator](https://github.com/riscv/riscv-isa-sim.git) as follows.

``` bash
$ git clone https://github.com/riscv/riscv-isa-sim.git
$ cd riscv-isa-sim
$ export RISCV=/path/to/install
$ mkdir build && cd build
$ ../configure --prefix=$RISCV
$ make
$ cd ../../
```

Then, you can clone this repository and compile it.

``` bash
$ git clone https://github.com/kohnakagawa/riscv_alnum_inst_finder
$ make
$ make run
```

### alphanumeric instructions

- for RV32

```
bge
bgeu
blt
bltu
c.addi16sp
c.fld
c.fldsp
c.flw
c.flwsp
c.jal
c.li
c.lui
c.lw
c.lwsp
csrc
csrci
csrrc
csrrci
csrrsi
csrrwi
csrwi
fcvt.d.q
fmadd.d
fmadd.q
fmadd.s
fmsub.d
fmsub.q
fmsub.s
fnmadd.d
fnmadd.q
fnmadd.s
fnmsub.d
fnmsub.q
fnmsub.s
j
jal
lui
sra
vadc.vim
vadc.vxm
vmadc.vim
vmadc.vxm
vmfeq.vf
vmfgt.vf
vmfle.vf
vmflt.vf
vmfne.vf
vmford.vf
vmsbc.vxm
vmseq.vi
vmseq.vx
vmsgtu.vi
vmsgtu.vx
vmsle.vi
vmsle.vx
vmsleu.vi
vmsleu.vx
vmslt.vx
vmsltu.vx
vmsne.vi
vmsne.vx
vrgather.vi
vrgather.vx
vsbc.vxm
vsetvli
vslide1up.vx
vslideup.vi
vslideup.vx
```

- for RV64

```
bge
bgeu
blt
bltu
c.addi16sp
c.addiw
c.fld
c.fldsp
c.ld
c.ldsp
c.li
c.lui
c.lw
c.lwsp
csrc
csrci
csrrc
csrrci
csrrsi
csrrwi
csrwi
fcvt.d.q
fmadd.d
fmadd.q
fmadd.s
fmsub.d
fmsub.q
fmsub.s
fnmadd.d
fnmadd.q
fnmadd.s
fnmsub.d
fnmsub.q
fnmsub.s
j
jal
lui
sra
vadc.vim
vadc.vxm
vmadc.vim
vmadc.vxm
vmfeq.vf
vmfgt.vf
vmfle.vf
vmflt.vf
vmfne.vf
vmford.vf
vmsbc.vxm
vmseq.vi
vmseq.vx
vmsgtu.vi
vmsgtu.vx
vmsle.vi
vmsle.vx
vmsleu.vi
vmsleu.vx
vmslt.vx
vmsltu.vx
vmsne.vi
vmsne.vx
vrgather.vi
vrgather.vx
vsbc.vxm
vsetvli
vslide1up.vx
vslideup.vi
vslideup.vx
```

There are no store instructions as pointed out by [this gist](https://gist.github.com/laanwj/99f5f720acf5f13903515da11f6a7b34). It may be impossible to implement self-contained alphanumeric shellcode in RISC-V ISA.

### ascii instructions

- for RV32

```
amoand.d
amoand.w
amoor.d
amoor.w
amoxor.d
amoxor.w
bge
bgeu
blt
bltu
c.addi16sp
c.fld
c.fldsp
c.flw
c.flwsp
c.jal
c.li
c.lui
c.lw
c.lwsp
csrc
csrci
csrr
csrrc
csrrci
csrrs
csrrsi
csrrwi
csrs
csrsi
csrwi
custom1.rd
custom1.rd.rs1
custom1.rd.rs1.rs2
custom1.rs1
custom1.rs1.rs2
custom2.rd
custom2.rd.rs1
custom2.rd.rs1.rs2
custom2.rs1
custom2.rs1.rs2
custom3.rd
custom3.rd.rs1
custom3.rd.rs1.rs2
custom3.rs1
custom3.rs1.rs2
fcvt.d.q
fcvt.s.q
fmadd.d
fmadd.q
fmadd.s
fmsub.d
fmsub.q
fmsub.s
fnmadd.d
fnmadd.q
fnmadd.s
fnmsub.d
fnmsub.q
fnmsub.s
fsd
fsgnjx.d
fsgnjx.q
fsgnjx.s
fsq
fsw
j
jal
lui
sd
sra
sraw
sw
vadc.vim
vadc.vxm
vamoandd.v
vamoandw.v
vamoord.v
vamoorw.v
vamoxord.v
vamoxorw.v
vand.vi
vand.vx
vcompress.vm
vext.x.v
vfmerge.vfm
vfsgnj.vf
vfsgnjn.vf
vfsgnjx.vf
viota.m
vmadc.vim
vmadc.vxm
vmand.mm
vmandnot.mm
vmerge.vim
vmerge.vxm
vmfeq.vf
vmfge.vf
vmfgt.vf
vmfirst.m
vmfle.vf
vmflt.vf
vmfne.vf
vmford.vf
vmnand.mm
vmnor.mm
vmor.mm
vmornot.mm
vmpopc.m
vmsbc.vxm
vmseq.vi
vmseq.vx
vmsgt.vi
vmsgt.vx
vmsgtu.vi
vmsgtu.vx
vmsle.vi
vmsle.vx
vmsleu.vi
vmsleu.vx
vmslt.vx
vmsltu.vx
vmsne.vi
vmsne.vx
vmsof.m
vmxnor.mm
vmxor.mm
vor.vi
vor.vx
vrgather.vi
vrgather.vx
vsbc.vxm
vsetvli
vslide1down.vx
vslide1up.vx
vslidedown.vi
vslidedown.vx
vslideup.vi
vslideup.vx
vsseg2e.v
vsseg2h.v
vsseg2w.v
vsseg3e.v
vsseg3h.v
vsseg3w.v
vsseg4e.v
vsseg4h.v
vsseg4w.v
vssseg2e.v
vssseg2h.v
vssseg2w.v
vssseg3e.v
vssseg3h.v
vssseg3w.v
vssseg4e.v
vssseg4h.v
vssseg4w.v
vxor.vi
vxor.vx
```

- for RV64

```
amoand.d
amoand.w
amoor.d
amoor.w
amoxor.d
amoxor.w
bge
bgeu
blt
bltu
c.addi16sp
c.addiw
c.fld
c.fldsp
c.ld
c.ldsp
c.li
c.lui
c.lw
c.lwsp
csrc
csrci
csrr
csrrc
csrrci
csrrs
csrrsi
csrrwi
csrs
csrsi
csrwi
custom1.rd
custom1.rd.rs1
custom1.rd.rs1.rs2
custom1.rs1
custom1.rs1.rs2
custom2.rd
custom2.rd.rs1
custom2.rd.rs1.rs2
custom2.rs1
custom2.rs1.rs2
custom3.rd
custom3.rd.rs1
custom3.rd.rs1.rs2
custom3.rs1
custom3.rs1.rs2
fcvt.d.q
fcvt.s.q
fmadd.d
fmadd.q
fmadd.s
fmsub.d
fmsub.q
fmsub.s
fnmadd.d
fnmadd.q
fnmadd.s
fnmsub.d
fnmsub.q
fnmsub.s
fsd
fsgnjx.d
fsgnjx.q
fsgnjx.s
fsq
fsw
j
jal
lui
sd
sra
sraw
sw
vadc.vim
vadc.vxm
vamoandd.v
vamoandw.v
vamoord.v
vamoorw.v
vamoxord.v
vamoxorw.v
vand.vi
vand.vx
vcompress.vm
vext.x.v
vfmerge.vfm
vfsgnj.vf
vfsgnjn.vf
vfsgnjx.vf
viota.m
vmadc.vim
vmadc.vxm
vmand.mm
vmandnot.mm
vmerge.vim
vmerge.vxm
vmfeq.vf
vmfge.vf
vmfgt.vf
vmfirst.m
vmfle.vf
vmflt.vf
vmfne.vf
vmford.vf
vmnand.mm
vmnor.mm
vmor.mm
vmornot.mm
vmpopc.m
vmsbc.vxm
vmseq.vi
vmseq.vx
vmsgt.vi
vmsgt.vx
vmsgtu.vi
vmsgtu.vx
vmsle.vi
vmsle.vx
vmsleu.vi
vmsleu.vx
vmslt.vx
vmsltu.vx
vmsne.vi
vmsne.vx
vmsof.m
vmxnor.mm
vmxor.mm
vor.vi
vor.vx
vrgather.vi
vrgather.vx
vsbc.vxm
vsetvli
vslide1down.vx
vslide1up.vx
vslidedown.vi
vslidedown.vx
vslideup.vi
vslideup.vx
vsseg2e.v
vsseg2h.v
vsseg2w.v
vsseg3e.v
vsseg3h.v
vsseg3w.v
vsseg4e.v
vsseg4h.v
vsseg4w.v
vssseg2e.v
vssseg2h.v
vssseg2w.v
vssseg3e.v
vssseg3h.v
vssseg3w.v
vssseg4e.v
vssseg4h.v
vssseg4w.v
vxor.vi
vxor.vx
```

For ascii, store instructions (`sd` and `sw`) are available unlike alphanumeric instructions. It enable us to write some data into a memory. Someone may consider self-contained shellcode is possible with ascii instructions, but it is not so easy.

In RISC-V ISA, `ecall` opcode includes null byte. To execute `ecall` in the self-contained shellcode, it is necessary to write `ecall` instruction to a memory, and jump to its address. However, for ascii instructions, only `j` and `jal` (relative jump instructions with respect to `pc`) are available, not `jalr` (relative jump instruction with respect to a general purpose register). Even though `ecall` is written to a memory, there is no way to jump to the address.

To my best knowledge, it is impossible to implement self-contained alphanumeric/ascii shellcode in RISC-V ISA. Someone may have a better idea.
