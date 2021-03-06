<h1>VEX Operations and Semantics</h1>

<h2>Table of Contents</h2>


## ALU Operations ##

| **Operation** | **Type** | **Opcode** | **Mnemonic** | **Description** |
|:--------------|:---------|:-----------|:-------------|:----------------|
| ADD    |  I |  `1000001` |  `ALU_ADD   ` | Add |
| AND    |  I |  `1000011` |  `ALU_AND   ` | Bitwise AND |
| ANDC   | I|  `1000100` |  `ALU_ANDC  ` | Bitwise complement and AND |
| MAX    | I|  `1000101` |  `ALU_MAX   ` | Maximum signed |
| MAXU   |  I |  `1000110` |  `ALU_MAXU  ` | Maximum unsigned |
| MIN    |  I |  `1000111` |  `ALU_MIN   ` | Minimum signed |
| MINU   |  I |  `1001000` |  `ALU_MINU  ` | Minimum unsigned |
| OR     |  I |  `1001001` |  `ALU_OR    ` | Bitwise OR |
| ORC    | I|  `1001010` |  `ALU_ORC   ` | Bitwise complement and OR |
| SH1ADD | I|  `1001011` |  `ALU_SH1ADD` | Shift left 1 and add |
| SH2ADD | I|  `1001100` |  `ALU_SH2ADD` | Shift left 2 and add |
| SH3ADD | I|  `1001101` |  `ALU_SH3ADD` | Shift left 3 and add |
| SH4ADD | I|  `1001110` |  `ALU_SH4ADD` | Shift left 4 and add |
| SHL    | I|  `1001111` |  `ALU_SHL   ` | Shift left |
| SHR    | I|  `1010000` |  `ALU_SHR   ` | Shift right signed |
| SHRU   | I|  `1010001` |  `ALU_SHRU  ` | Shift right unsigned |
| SUB    | VI|  `1010010` |  `ALU_SUB   ` | Subtract |
| SXTB   | VII|  `1010011` |  `ALU_SXTB  ` | Sign extend byte |
| SXTH   | VII|  `1010100` |  `ALU_SXTH  ` | Sign extend half word |
| ZXTB   | VII|  `1010101` |  `ALU_ZXTB  ` | Zero extend byte |
| ZXTH   | VII|  `1010110` |  `ALU_ZXTH  ` | Zero extend half word |
| XOR    | I|  `1010111` |  `ALU_XOR   ` | Bitwise XOR |
| MOV    | VII|  `1011000` |  `ALU_MOV   ` | Copy `s1` to other location |
| CMPEQ  | II|  `1011001` |  `ALU_CMPEQ ` | Compare: equal |
| CMPGE  | II|  `1011010` |  `ALU_CMPGE ` | Compare: greater equal signed |
| CMPGEU | II|  `1011011` |  `ALU_CMPGEU` | Compare: greater equal unsigned |
| CMPGT  | II|  `1011100` |  `ALU_CMPGT ` | Compare: greater signed |
| CMPGTU | II|  `1011101` |  `ALU_CMPGTU` | Compare: greater unsigned |
| CMPLE  | II|  `1011110` |  `ALU_CMPLE ` | Compare: less than equal signed |
| CMPLEU | II|  `1011111` |  `ALU_CMPLEU` | Compare: less than equal unsigned |
| CMPLT  | II|  `1100000` |  `ALU_CMPLT ` | Compare: less than signed |
| CMPLTU | II|  `1100001` |  `ALU_CMPLTU` | Compare: less than unsigned |
| CMPNE  | II|  `1100010` |  `ALU_CMPNE ` | Compare: not equal |
| NANDL  | II|  `1100011` |  `ALU_NANDL ` | Logical NAND |
| NORL   | II|  `1100100` |  `ALU_NORL  ` | Logical NOR |
| ORL    | II|  `1100110` |  `ALU_ORL   ` | Logical OR |
| MTB    | V|  `1100111` |  `ALU_MTB   ` | Move GR to BR |
| ANDL   | II|  `1101000` |  `ALU_ANDL  ` | Logical AND |
| ADDCG | IV|  `1111---` |  `ALU_ADDCG` | Add with carry and generate carry. |
| DIVS  | IV|  `1110---` |  `ALU_DIVS ` | Division step with carry and generate carry |
| SLCT  | III|  `0111---` |  `ALU_SLCT ` | Select `s1` on true condition. (exceptional opcode) |
| SLCTF | III|  `0110---` |  `ALU_SLCTF` | Select `s1` on false condition. (exceptional opcode) |
| N/A| N/A| `1000000`  | N/A|  ALU r-OP  |
| N/A| N/A| `1000010`  | N/A|  ALU r-OP  |
| N/A| N/A| `1100101`  | N/A|  ALU r-OP  |
| N/A| N/A| `1101001`  | N/A|  ALU r-OP  |
| N/A| N/A| `1101010`  | N/A|  ALU r-OP  |
| N/A| N/A| `1101011`  | N/A|  ALU r-OP  |
| N/A| N/A| `1101100`  | N/A|  ALU r-OP  |
| N/A| N/A| `1101101`  | N/A|  ALU r-OP  |
| N/A| N/A| `1101110`  | N/A|  ALU r-OP  |
| N/A| N/A| `1101111`  | N/A|  ALU r-OP  |

## MUL Operations ##

| **Operation** | **Type** | **Opcode** | **Mnemonic** | **Description** |
|:--------------|:---------|:-----------|:-------------|:----------------|
|MPYLL  |I | `0000001` | `MUL_MPYLL ` |Multiply signed low 16 x low 16 bits |
|MPYLLU |I | `0000010` | `MUL_MPYLLU` |Multiply unsigned low 16 x low 16 bits |
|MPYLH  |I | `0000011` | `MUL_MPYLH ` |Multiply signed low 16 (`s1`) x high 16 (`s2`) bits |
|MPYLHU |I | `0000100` | `MUL_MPYLHU` |Multiply unsigned low 16 (`s1`) x high 16 (`s2`) bits |
|MPYHH  |I | `0000101` | `MUL_MPYHH ` |Multiply signed high 16 x high 16 bits |
|MPYHHU |I | `0000110` | `MUL_MPYHHU` |Multiply unsigned high 16 x high 16 bits |
|MPYL   |I | `0000111` | `MUL_MPYL  ` |Multiply signed low 16 (`s2`) x 32 (`s1`) bits |
|MPYLU  |I | `0001000` | `MUL_MPYLU ` |Multiply unsigned low 16 (`s2`) x 32 (`s1`) bits |
|MPYH   |I | `0001001` | `MUL_MPYH  ` |Multiply signed high 16 (`s2`) x 32 (`s1`) bits |
|MPYHU  |I | `0001010` | `MUL_MPYHU ` |Multiply unsigned high 16 (`s2`) x 32 (`s1`) bits |
|MPYHS  |I | `0001011` | `MUL_MPYHS ` |Multiply signed high 16 (`s2`) x 32 (`s1`) bits, shift left 16  |
| N/A|N/A|`0001100`  |N/A| MUL r-OP  |
| N/A|N/A|`0001101`  |N/A| MUL r-OP  |
| N/A|N/A|`0001110`  |N/A| MUL r-OP  |
| N/A|N/A|`0001111`  |N/A| MUL r-OP  |


## CTRL Operations ##

| **Operation** | **Type** | **Opcode** | **Mnemonic** | **Description** |
|:--------------|:---------|:-----------|:-------------|:----------------|
|GOTO<sup>1</sup> |XIII| `0100001` | `CTRL_GOTO  ` |Unconditional relative jump|
|IGOTO<sup>1</sup> |XIX| `0100010` | `CTRL_IGOTO ` |Unconditional absolute indirect jump to link register|
|CALL<sup>1</sup> |XVI| `0100011` | `CTRL_CALL  ` |Unconditional relative call|
|ICALL<sup>1</sup> |XX| `0100100` | `CTRL_ICALL ` |Unconditional absolute indirect call to link register|
|BR     |VIII| `0100101` | `CTRL_BR    ` |Conditional relative branch on true condition|
|BRF    |VIII| `0100110` | `CTRL_BRF   ` |Conditional relative branch on false condition|
|RETURN |XVII| `0100111` | `CTRL_RETRN` |Pop stack frame and goto link register|
|RFI    |XIV| `0101000` | `CTRL_RFI   ` |Return from interrupt|
|XNOP   |XV| `0101001` | `CTRL_XNOP  ` |Multicycle NOP  |
| N/A| N/A| `0100000`  | N/A| CTRL r-OP  |
| N/A| N/A| `0101100`  | N/A| CTRL r-OP  |
| N/A| N/A| `0101101`  | N/A| CTRL r-OP  |
| N/A| N/A| `0101110`  | N/A| CTRL r-OP  |
| N/A| N/A| `0101111`  | N/A| CTRL r-OP  |

<sup>1</sup> According a to a message on the VEX forum, the **CALL** & **ICALL** and **GOTO** & **IGOTO** operations are overloaded in the latest VEX compiler, so **ICALL** and **IGOTO** are obsolete. These are still supported in its original form to stay compliant to the original VEX ISA. See http://www.vliw.org/vex/viewtopic.php?t=52 for more information.


## MEM Operations ##

| **Operation** | **Type** | **Opcode** | **Mnemonic** | **Description** |
|:--------------|:---------|:-----------|:-------------|:----------------|
|LDW  |X | `0010001` | `MEM_LDW ` |Load word|
|LDH  |X | `0010010` | `MEM_LDH ` |Load halfword signed|
|LDHU |X | `0010011` | `MEM_LDHU` |Load halfword unsigned|
|LDB  |X | `0010100` | `MEM_LDB ` |Load byte signed|
|LDBU |X | `0010101` | `MEM_LDBU` |Load byte unsigned|
|STW  |XI| `0010110` | `MEM_STW ` |Store word|
|STH  |XI| `0010111` | `MEM_STH ` |Store halfword|
|STB  |XI| `0011000` | `MEM_STB ` |Store byte|
|PFT  |XII| `0011001` | `MEM_PFT ` |Prefetch|
| N/A| N/A| `0011010`  | N/A| MEM r-OP  |
| N/A| N/A| `0011011`  | N/A| MEM r-OP  |
| N/A| N/A| `0011101`  | N/A| MEM r-OP  |
| N/A| N/A| `0011110`  | N/A| MEM r-OP  |
| N/A| N/A| `0010000`  | N/A| MEM r-OP  |


## Miscellaneous Operations ##

| **Operation** | **Type** | **Opcode** | **Mnemonic** | **Description** |
|:--------------|:---------|:-----------|:-------------|:----------------|
|STOP  |XIV| `0011111` | `STOP ` |STOP operation|
|NOP   |XIV| `0000000` | `NOP  ` |No operation  |
|SEND |IX| `0101010` | `INTR_SEND` |Send `s1` to the path identified by `path`|
|RECV |XVIII| `0101011` | `INTR_RECV` |Assigns the value from the path identified by `path` to `t`|
| N/A |N/A| `0011100` | `SYL_FOLLOW` |Syllable contains second half of long immediate|

## VEX Semantics ##
| **Type** | **Semantics** |
|:---------|:--------------|
|I  | `operation $r0.t = $r0.s1, $r0.s2` |
|   | `operation $r0.t = $r0.s1, s2` |
|II | `operation $r0.t = $r0.s1, $r0.s2`  |
|   | `operation $r0.t = $r0.s1, s2` |
|   | `operation $b0.b = $r0.s1, $r0.s2` |
|   | `operation $b0.b = $r0.s1, s2` |
|III  | `operation $r0.t = $b0.b1, $r0.s1, $r0.s2`  |
|	 | `operation $r0.t = $b0.b1, $r0.s1, s2`  |
|IV  |  `operation $r0.t, $b0.b = $b0.b1, $r0.s1, $r0.s2`  |
|V  | `operation $b0.b = $r0.s1`  |
|VI  | `operation $r0.t = $r0.s2, $r0.s1`  |
|	 | `operation $r0.t = s2, $r0.s1`  |
|VII  | `operation $r0.t = $r0.s1`  |
|VIII  | `operation $b0.b, label`  |
|IX  | `operation $r0.s1, path`  |
|X  | `operation $r0.t = offset[$r0.s1]`  |
|XI  | `operation offset[$r0.s1] = $r0.s2`  |
|XII  | `operation offset[$r0.s1]`  |
|XIII  | `operation label`  |
|  |`operation $r0.lr`  |
|XIV  | `operation`  |
|XV  | `operation n`  |
|XVI | `operation $l0.t = label`  |
|  |`operation $l0.t = $l0.t`|
|XVII  | `operation $r0.t = $r0.t, label, $r0.lr`  |
|XVIII  | `operation $r0.t = path`  |
|XIX  | `operation $r0.lr`  |
|XX  | `operation $l0.t = $l0.t`  |

|`operation` | The operation as presented in one of the lists above, lowercase |
|:-----------|:----------------------------------------------------------------|
|`$r0.#` | GR register where `#` can be  `t` (target), `s1` (source 1), `s2` (source 2) or `lr` (link register) |
|`$b0.#` | BR register where `#` can be `b` (target) or `b1` (source 1) |
|`s2` | Immediate operand (without preceeding `$r0.`) |
|`label` | Label to jump to when branching |
|`offset` | Offset used when loading or storing to data memory |
|`n` | Number of cycles (in **XNOP**) |
|`path` | Path for sending/receiving inter-cluster contents (unsupported in r-VEX) |