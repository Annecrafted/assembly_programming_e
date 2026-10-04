# Subtraction Operations and EFLAGS Analysis

This directory analyzes the `SUB` and `SBB` instructions and their effect on the EFLAGS register.

---

## Program 1: `sub1.asm` (50 - 80)

- **Result:** `AL = 0xE2` (-30)
- **EFLAGS:** `[ CF PF SF IF ]`

### Flag Analysis

- **CF (Set):** A borrow occurred because 50 is smaller than 80.
- **SF (Set):** The result is negative.
- **PF (Set):** The result contains an even number of 1 bits.
- **ZF (Cleared):** The result is not zero.
- **OF (Cleared):** No signed overflow occurred because the result fits within the 8-bit signed range.

---

## Program 2: `sub2.asm` (1000 - 2000)

- **Result:** `AX = 0xFC18` (-1000)
- **EFLAGS:** `[ CF PF SF IF ]`

### Flag Analysis

- **CF (Set):** A borrow occurred because 1000 is smaller than 2000.
- **SF (Set):** The result is negative.
- **PF (Set):** The lower byte contains an even number of 1 bits.
- **ZF (Cleared):** The result is not zero.
- **OF (Cleared):** No signed overflow occurred because the result fits within the 16-bit signed range.

---

## Program 3: `sub3.asm` (Subtract with Borrow)

- **Result:** `AX = 0xFFFE` (-2)
- **EFLAGS:** `[ SF IF ]`

### Flag Analysis

- The first `SUB` instruction generated a borrow, setting the Carry Flag.
- `SBB` used that borrow in the next subtraction, producing a result of `-2`.
- **SF (Set):** The result is negative.
- **CF (Cleared):** No borrow remained after the final subtraction.
- **ZF (Cleared):** The result is not zero.
- **OF (Cleared):** No signed overflow occurred.
- **PF (Cleared):** The result contains an odd number of 1 bits.