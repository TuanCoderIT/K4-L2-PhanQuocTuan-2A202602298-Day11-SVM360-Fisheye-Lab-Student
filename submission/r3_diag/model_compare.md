# L / R / M

L/R/M là thứ tự box in-scope theo XML của từng frame.

## adasind_258420.jpg
- L1+R1: LR_noM (edge)
- L2+R6+M2: LRM (edge)
- L4+R4: LR_noM (center)
- L3+R8: LR_noM (center)
- L10+R7+M12: LRM (mid)
- L8+R2+M9: LRM (mid)
- L6+R3: LR_noM (mid)
- L5+M6: LM_noR (mid)
- L7: L_only (mid)
- L9: L_only (mid)
- L11: L_only (mid)
- R5: R_only (mid)
- M3: M_only (mid)
- M4: M_only (edge)
- M5: M_only (mid)
- M7: M_only (mid)
- M8: M_only (center)
- M10: M_only (mid)
- M11: M_only (center)
## adasind_270517.jpg
- L5+R6+M1: LRM (mid)
- L8+R4: LR_noM (center)
- L7+R1+M4: LRM (center)
- L1+R3+M2: LRM (edge)
- L2+R2: LR_noM (center)
- L4+R7+M8: LRM (mid)
- L6+R5+M3: LRM (center)
- M5: M_only (mid)
- M6: M_only (center)
- M7: M_only (center)
- M9: M_only (center)
- M10: M_only (mid)
- M11: M_only (mid)
## adasind_310008.jpg
- L2+R1: LR_noM (mid)
- L4+R2+M3: LRM (edge)
- L5+R4+M4: LRM (edge)
- L3+R3+M1: LRM (edge)
- L1+R5+M2: LRM (edge)
- M6: M_only (mid)
- M7: M_only (mid)

## Zone × cell
| zone | LRM | LR_noM | LM_noR | L_only | RM_noL | R_only | M_only |
|---|---|---|---|---|---|---|---|
| center | 2 | 4 | 0 | 0 | 0 | 0 | 5 |
| mid | 4 | 2 | 1 | 3 | 0 | 1 | 9 |
| edge | 6 | 1 | 0 | 0 | 0 | 0 | 1 |
