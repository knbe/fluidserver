---
time: 202302141345
title: "constructing the mechanical stress tensor"
type: note
---

¶ consider a small area element, d↗A. momentum flows through this area in the 
  +ve direction. the MASS FLOW RATE thru the surface is
  ```
    ρ↗v ⦁ d↗A = dot(momentumͺdensity, vectorͺareaͺelement)
  ```
  multiply by velocity to get the MOMENTUM FLOW RATE:
  ```
    ḍ₍t₎⬀p = (ρ⬀v)·(⬀v⦁d⬀A)
  ```
  this is just the force ˝⬀F = ḍ⬀p˝ across the area element ˝d↗A˝. from the 
  definition of the stress tensor, you can compute the force by inserting ˝d↗A˝ 
  into the 2nd arg of a stress tensor, 
  ```
    ↗F = d₍t₎↗p = T(ͺͺ,d↗A) 
  ```
  in index notation
  ```
    F⟦i⟧ = d₍t₎p⟦i⟧ = (p·v⟦i⟧)·v⟦j⟧·dA⟦j⟧ = T⟦ij⟧·dA⟦j⟧
  ```
  from the middle expression, the stress tensor is
  ```
    T⟦ij⟧ = ρ·v⟦i⟧·v⟦j⟧
  ```
  or
  ```
    T = ρ·↗v⊗↗v
  ```

¶ so the mechanical stress tensor is the MOMENTUM FLUX (the momentum flow rate).
  - >> why is it called the MECHANICAL stress tensor? thorne: flow rate of 
    *mechanical momentum*. as opposed to what? <<
  - so on this note should have written ˝T = T₍m₎˝. this is specifically the 
    mechanical stress tensor.
