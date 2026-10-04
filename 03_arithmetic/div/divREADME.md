# Division Operations and EFLAGS Analysis

This directory analyzes the `DIV` instruction and its effect on the EFLAGS register.

---

## Program 1: `div1.asm`

- **Result:** 100 ÷ 7 = 14 remainder 2
- **EFLAGS:** [ IF ]

### Flag Analysis

- The `DIV` instruction leaves CF, OF, SF, ZF, AF, and PF undefined.
- Because these flags are undefined, they cannot be used to determine the outcome of the division.

---

## Program 2: `div2.asm`

- **Result:** 50000 ÷ 300 = 166 remainder 200
- **EFLAGS:** [ IF ]

### Flag Analysis

- The `DIV` instruction leaves CF, OF, SF, ZF, AF, and PF undefined.
- Because these flags are undefined, they cannot be used to determine the outcome of the division.

---

## Program 3: `div3.asm`

- **Result:** 300000 ÷ 1 = 300000 remainder 0
- **EFLAGS:** [ IF ]

### Flag Analysis

- The `DIV` instruction leaves CF, OF, SF, ZF, AF, and PF undefined.
- Because these flags are undefined, they cannot be used to determine the outcome of the division.