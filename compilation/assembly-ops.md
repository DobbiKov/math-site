# Cheatsheet MIPS Assembly

## 1. Chargement et stockage (mémoire)

| Instruction       | Syntaxe          | Description                                                                  | Exemple          | Effet mémoire             |
| ----------------- | ---------------- | ---------------------------------------------------------------------------- | ---------------- | ------------------------- |
| **lw**            | `lw $rt, d($rs)` | Charge un mot (4 octets) depuis la mémoire à l’adresse `$rs + d` vers `$rt`. | `lw $t0, 8($a1)` | Copie `Mem[$a1+8] → $t0`. |
| **sw**            | `sw $rt, d($rs)` | Stocke le contenu de `$rt` en mémoire à l’adresse `$rs + d`.                 | `sw $t0, 0($t1)` | Copie `$t0 → Mem[$t1+0]`. |
| **la**            | `la $rt, label`  | Charge l’adresse d’une donnée.                                               | `la $a0, hw`     | `$a0 ← adresse de hw`.    |
| **li** (pseudo)   | `li $rt, imm`    | Charge une constante immédiate (peut générer 1 ou 2 instructions).           | `li $t0, 42`     | `$t0 ← 42`.               |
| **move** (pseudo) | `move $rd, $rs`  | Copie un registre dans un autre.                                             | `move $t1, $t0`  | `$t1 ← $t0`.              |

---

## 2. Arithmétique et logique

| Instruction         | Syntaxe                  | Description                                        | Exemple             | Effet                               |
| ------------------- | ------------------------ | -------------------------------------------------- | ------------------- | ----------------------------------- |
| **add**             | `add $rd, $rs, $rt`      | Addition signée.                                   | `add $t0, $t1, $t2` | `$t0 ← $t1 + $t2`.                  |
| **addi**            | `addi $rt, $rs, imm`     | Addition avec immédiat.                            | `addi $t0, $t0, 5`  | `$t0 ← $t0 + 5`.                    |
| **sub**             | `sub $rd, $rs, $rt`      | Soustraction.                                      | `sub $t0, $t1, $t2` | `$t0 ← $t1 - $t2`.                  |
| **mul**             | `mul $rd, $rs, $rt`      | Multiplication.                                    | `mul $t0, $t1, $t2` | `$t0 ← $t1 * $t2`.                  |
| **div**             | `div $rs, $rt`           | Division entière. Quotient → `$lo`, reste → `$hi`. | `div $t1, $t2`      | `$lo ← $t1 / $t2, $hi ← $t1 % $t2`. |
| **mflo/mfhi**       | `mflo $rd` / `mfhi $rd`  | Récupère résultat de division/multiplication.      | `mflo $t0`          | `$t0 ← lo`.                         |
| **and / or / xor**  | `and $rd, $rs, $rt` etc. | Logique bit-à-bit.                                 | `and $t0, $t1, $t2` | `$t0 ← $t1 & $t2`.                  |
| **sll / srl / sra** | `sll $rd, $rt, shamt`    | Décalage gauche/droite (arith/log).                | `sll $t1, $t1, 1`   | `$t1 ← $t1 << 1`.                   |
| **slt**             | `slt $rd, $rs, $rt`      | Met `$rd=1` si `$rs<$rt`, sinon 0.                 | `slt $t0, $t1, $t2` | `$t0 ← ($t1<$t2)?1:0`.              |

---

## 3. Comparaisons et branchements

| Instruction                        | Syntaxe               | Description                        | Exemple                | Effet                 |
| ---------------------------------- | --------------------- | ---------------------------------- | ---------------------- | --------------------- |
| **beq**                            | `beq $rs, $rt, label` | Branche si `$rs == $rt`.           | `beq $t0, $t1, equal`  | PC ← label si égal.   |
| **bne**                            | `bne $rs, $rt, label` | Branche si `$rs != $rt`.           | `bne $t0, $zero, loop` | PC ← loop si ≠0.      |
| **blt / ble / bgt / bge** (pseudo) | `blt $rs, $rt, L`     | Branche si `<, ≤, >, ≥`.           | `blt $t0, $t1, L`      | PC ← L si `$t0<$t1`.  |
| **beqz / bnez**                    | `beqz $rs, label`     | Branche si `$rs==0` ou `$rs≠0`.    | `bnez $t0, loop`       | PC ← loop si `$t0≠0`. |
| **b**                              | `b label`             | Branche inconditionnelle (pseudo). | `b end`                | PC ← end.             |

---

## 4. Sauts et fonctions

| Instruction | Syntaxe     | Description                                | Exemple                       |
| ----------- | ----------- | ------------------------------------------ | ----------------------------- |
| **j**       | `j label`   | Saut inconditionnel à `label`.             | `j main`                      |
| **jr**      | `jr $rs`    | Saut à l’adresse dans `$rs`.               | `jr $ra` (retour de fonction) |
| **jal**     | `jal label` | Appel fonction : PC ← label, `$ra ← PC+4`. | `jal printf`                  |
| **jalr**    | `jalr $rs`  | Comme jal mais adresse dans un registre.   | `jalr $t0`                    |

---

## 5. Pile et mémoire

| Instruction       | Syntaxe                          | Description        | Exemple         |
| ----------------- | -------------------------------- | ------------------ | --------------- |
| **push** (pseudo) | `addi $sp,$sp,-4; sw $rt,0($sp)` | Empile `$rt`.      | `sw $ra,0($sp)` |
| **pop** (pseudo)  | `lw $rt,0($sp); addi $sp,$sp,4`  | Dépile dans `$rt`. | `lw $ra,0($sp)` |

---

## 6. Appels système (syscall)

* Avant `syscall`, placer un code service dans `$v0`, et arguments dans `$a0..a3`.

| Service      | Code | Argument(s)     | Exemple                         |
| ------------ | ---- | --------------- | ------------------------------- |
| Print int    | 1    | `$a0 = entier`  | `li $v0,1; li $a0,42; syscall`  |
| Print string | 4    | `$a0 = adresse` | `li $v0,4; la $a0,msg; syscall` |
| Read int     | 5    | → `$v0`         | `li $v0,5; syscall`             |
| Exit         | 10   | –               | `li $v0,10; syscall`            |

