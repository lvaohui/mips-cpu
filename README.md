# Logisim 开发单周期MIPS处理器

> 支持指令集MIPS-C7: addu, subu, ori, lw, sw, beq, lui


测试代码
```assembly
lui $t0,1
lui $t1,1
lui $t2,1
ori $t0,$t0,100
ori $t1,$t1,1
subu $t0,$t0,$t2
subu $t1,$t1,$t2
lui $t2,0
lui $t3,0
lui $t4,0
for:addu $t2,$t2,$t0
addu $t4,$t4,$t0
subu $t0,$t0,$t1
addu $t2,$t2,$t0
addu $t3,$t3,$t0
subu $t0,$t0,$t1
beq $t0,$zero,lab
beq $zero,$zero,for
lab:sw $t2,0($zero)
sw $t3,1($zero)
sw $t4,2($zero)
lw $t5,0($zero)
lw $t6,1($zero)
lw $t7,2($zero)
```
