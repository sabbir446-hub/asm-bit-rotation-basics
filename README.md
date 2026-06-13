# 8086 Assembly Bitwise Rotate Left (ROL)

A basic 8086 Assembly Language program written in MASM/TASM syntax that demonstrates bitwise circular shifting using the **`ROL` (Rotate Left)** instruction and DOS interrupts (`INT 21H`).

## 🚀 Project Overview

This program captures a single-digit number input from the user, converts it from ASCII to its actual numeric decimal value, applies a bitwise left-rotation by 1 position, and converts the result back to ASCII format to display it on the console screen.

## 🛠️ How It Works & Bitwise Logic

Unlike logical shifting (`SHL`), where the bits falling off the edge are lost and replaced by zeros, **Rotation (`ROL`)** wraps the bits around in a circular fashion. 

### The Rotation Logic ($ROL$):
When you execute `ROL BL, 1`, every bit inside the 8-bit `BL` register shifts left by one slot. The **Most Significant Bit (MSB)** or the leftmost bit that leaves the register is moved into the **Least Significant Bit (LSB)** or rightmost slot, as well as copied into the Carry Flag (CF).

#### Bitwise Example (Inputting the number `1`):
1. **ASCII Conversion:** Input `'1'` (ASCII 49) $\rightarrow 49 - 48 =$ numeric value **`1`**.
2. **Binary Representation:** Decimal `1` in an 8-bit register is `0000 0001`.
3. **Execution of `ROL BL, 1`:** * Before: `0 0 0 0  0 0 0 1` (The leftmost bit is `0`, rightmost is `1`)
   * After:  `0 0 0 0  0 0 1 0` (The leftmost `0` wrapped around to the rightmost spot, and everything shifted left).
4. **Result:** Binary `0000 0010` is decimal **`2`**.
