# L / R / M

L/R/M là thứ tự box in-scope theo XML của từng frame.

## adasind_249480.jpg
- L1+R2+M5: LRM (mid)
- L2+R1+M1: LRM (center)
- M2: M_only (center)
- M4: M_only (center)
- M6: M_only (edge)
## adasind_261480.jpg
- L4+R7+M9: LRM (mid)
- L1+R3+M3: LRM (mid)
- L8+R2+M7: LRM (mid)
- L2+R6: LR_noM (mid)
- L6+R4: LR_noM (center)
- L7+R1+M1: LRM (center)
- L3+R5: LR_noM (mid)
- L5: L_only (mid)
- M2: M_only (mid)
- M5: M_only (mid)
- M6: M_only (mid)
- M8: M_only (mid)
- M10: M_only (center)
- M11: M_only (mid)
- M12: M_only (center)
- M13: M_only (mid)
## adasind_265065.jpg
- L2+R2+M2: LRM (mid)
- L4+R1+M3: LRM (mid)
- L5+R8+M5: LRM (mid)
- L3+R3+M1: LRM (mid)
- L6+R6+M6: LRM (mid)
- L1: L_only (center)
- R4+M4: RM_noL (center)
- R5+M7: RM_noL (mid)
- R7: R_only (mid)
- M8: M_only (mid)

## Zone × cell
| zone | LRM | LR_noM | LM_noR | L_only | RM_noL | R_only | M_only |
|---|---|---|---|---|---|---|---|
| center | 2 | 1 | 0 | 1 | 1 | 0 | 4 |
| mid | 9 | 2 | 0 | 1 | 1 | 1 | 7 |
| edge | 0 | 0 | 0 | 0 | 0 | 0 | 1 |
