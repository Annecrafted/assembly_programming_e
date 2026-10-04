# Multiplication Operations and EFLAGS Analysis

This directory analyzes the `MUL` instruction and its effect on the EFLAGS register.

---

## Program 1: `mul1.asm` (8-Bit Multiplication)

- **Result:** `AX = 0x00FA`
- **EFLAGS:** `[ IF ]`

### Flag Analysis

- **CF (Cleared):** The upper half of the product (`AH`) is zero, so the result fits within the lower register.
- **OF (Cleared):** No overflow occurred because the upper half of the product is zero.
- **ZF, SF, PF:** Undefined after a `MUL` instruction.

---

## Program 2: `mul2.asm` (16-Bit Multiplication)

- **Result:** `DX:AX = 0x000927C0`
- **EFLAGS:** `[ CF IF OF ]`

### Flag Analysis

- **CF (Set):** The upper 16 bits of the product (`DX`) are non-zero, indicating the result exceeded 16 bits.
- **OF (Set):** Overflow occurred because part of the product was stored in `DX`.
- **ZF, SF, PF:** Undefined after a `MUL` instruction.

---

## Program 3: `mul3.asm` (32-Bit Multiplication)

- **Result:** Product stored in `EDX:EAX`
- **EFLAGS:** `[ CF IF OF ]`

### Flag Analysis

- **CF (Set):** The upper 32 bits (`EDX`) are non-zero, indicating the product exceeded 32 bits.
- **OF (Set):** Overflow occurred because part of the product was stored in `EDX`.
- **ZF, SF, PF:** Undefined after a `MUL` instruction.