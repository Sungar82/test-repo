# Huayou Pipe-Forming Formulas

Transcribed from the original Chinese PDF: Huayou φ508–φ2540 Pipe Forming Machine Parameter Calculations. Equations are transcribed, not independently validated.

## 1. Forming angles

α₁ = acos(B / (π(D − t)))

α₂ = atan(π(D − 2t) sin α₁ / B)

α₃ = atan(πD sin α₁ / B)

## 2. Forming-roll inclination angles

γ₁ = acos((H − 360 + D/2) / (160 + R + D/2))

γ₃ = acos((H − 389 + D/2) / (160 + R + D/2))

## 3. Forming-roll openings

k₁ = sin γ₁ × (160 + R + D/2) − 150

k₃ = sin γ₃ × (160 + R + D/2) − 150

## 4. Forming-roll heights

H₁ = H + D/2 − cos γ₁ × (R + D/2) + R

H₂ = H + t

H₃ = H + D/2 − cos γ₃ × (R + D/2) + R

## 5. Other parameters

S = B / sin α₁

L_S = π(D − t) / sin α₁

L_max = π(D + Δ_max)

L = πD

L_min = π(D + Δ_min)

V_out = V_weld × cos α₁

V_rot = V_weld × sin α₁

## Variables and source notes

B = steel strip working width; D = pipe outside diameter; t = wall thickness; H = pipe lower-surface reference height; R = forming-roll radius. The source gives H = 590 mm and R = 85 mm as reference values. Δ_max and Δ_min are diameter tolerances defined by the applicable production standard.

Angle units are degrees in the source. Confirm spreadsheet angle handling and independently validate formulas before production use.
