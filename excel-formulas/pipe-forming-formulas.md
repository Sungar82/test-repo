# Pipe-Forming Formulas — Excel Reference

## Input cells (mm unless stated otherwise)

| Cell | Parameter | Meaning |
|---|---|---|
| B2 | B | Strip working width |
| B3 | D | Pipe outside diameter |
| B4 | t | Wall thickness |
| B5 | H | Pipe lower-surface reference height |
| B6 | R | Forming-roll radius |
| B7 | Delta_max | Maximum diameter deviation |
| B8 | Delta_min | Minimum diameter deviation |
| B9 | V_weld | Welding speed (m/min) |

Use separate output cells for the calculated angles so the input cells remain unchanged. The formulas below assume input cells B2:B9 as listed, with outputs starting in D2.

## Forming angles (degrees)

D2 (alpha1): =DEGREES(ACOS(B2/(PI()*(B3-B4))))

D3 (alpha2): =DEGREES(ATAN(PI()*(B3-2*B4)*SIN(RADIANS(D2))/B2))

D4 (alpha3): =DEGREES(ATAN(PI()*B3*SIN(RADIANS(D2))/B2))

## Roll inclination angles (degrees)

D5 (gamma1): =DEGREES(ACOS((B5-360+B3/2)/(160+B6+B3/2)))

D6 (gamma3): =DEGREES(ACOS((B5-389+B3/2)/(160+B6+B3/2)))

## Roll openings (mm)

D7 (k1): =SIN(RADIANS(D5))*(160+B6+B3/2)-150

D8 (k3): =SIN(RADIANS(D6))*(160+B6+B3/2)-150

## Roll heights (mm)

D9 (H1): =B5+B3/2-COS(RADIANS(D5))*(B6+B3/2)+B6

D10 (H2): =B5+B4

D11 (H3): =B5+B3/2-COS(RADIANS(D6))*(B6+B3/2)+B6

## Other parameters

D12 (spiral pitch S): =B2/SIN(RADIANS(D2))

D13 (spiral line length Ls): =PI()*(B3-B4)/SIN(RADIANS(D2))

D14 (maximum circumference): =PI()*(B3+B7)

D15 (nominal circumference): =PI()*B3

D16 (minimum circumference): =PI()*(B3+B8)

D17 (pipe exit speed): =B9*COS(RADIANS(D2))

D18 (rotation-related speed component): =B9*SIN(RADIANS(D2))

## Important notes

- The source specifies H = 590 mm and R = 85 mm as reference values; enter these in B5 and B6 when appropriate.
- Excel trigonometric functions use radians, so RADIANS() is required when calculated angles are stored in degrees.
- ACOS requires an input between -1 and 1. Check the geometry if Excel returns an error.
- These formulas are transcribed from the source equations and have not been independently validated for machine operation. Verify against the original drawing and manufacturer before production use.
