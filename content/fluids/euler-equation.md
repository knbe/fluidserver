---
title: "euler equation"
type: long
---

¶ take the momentum conservation law for a fluid,
  ```
    𝝏₍t₎(ρ↗v) + ∇⦁T = ρ↗g
  ```
  differentiate then invoke the mass conservation law,
  ```
    𝝏₍t₎ρ + ∇⦁(ρ↗v) = 0
  ```
  you get the euler equation:
  ```
    Ɗ₍t₎↗v = 𝝏₍t₎↗v + (↗v⦁∇)↗v = -÷1ρ·∇p + ↗g
  ```

¶ the LHS is the advective derivative of ↗v, ie the acceleration of the fluid. 
  from the RHS, you can see there are two terms that cause the acceleration: 
  gravity, and the pressure gradient.

¶ in hydrostatics, ↗v = 0, and the euler equation reduces to the equation of 
  hydrostatic equilibrium:
  ```
    ∇p = ρ↗g
  ```
  or, a more general form is to replace ˝↗g˝ with ˝-∇φ˝
