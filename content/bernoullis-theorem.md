---
time: 202302211609
title: "bernoulli's theorem"
type: long
---

- >> what is the entropy of a fluid? what does it mean? <<

¶ bernoulli's principle: comes from conservation of energy.

  in a steady flow, the sum of all forms of energy is the same at all points 
  (free of viscous forces). KE + PE + internal energy = constant.

  means that an increase in speed of fluid occurs simultaneously with decrease 
  in static pressure.

¶ can derive bernoulli's principle from euler's equation (restatement of 
  newton's second law).

  momentum conservation law of an ideal fluid:
  ```
    𝝏₍t₎(ρ↗v) + ∇⦁T = ρ↗g
  ```
  - note: "ideal fluid" is a fluid where there's no dissipation.
  - >> what do you lose? <<

  conservation of mass, differential form:
  ```
    𝝏₍t₎ρ + ∇⦁(ρ↗v) = 0     𝓮𝓺{221}
  ```

  differentiate the momentum conservation law, substitute the mass law, you get 
  EULER's EQUATION
  ```
    Ɗ₍t₎↗v = 𝝏₍t₎↗v + (↗v⦁∇)↗v = -÷1ρ·∇p + ↗g
  ```
  - advective derivative on te LHS

  use {{< ℑ VORTICITY >}} : ˝↗ω  = ∇ × ↗v˝. write 
  ```
    ↗v × ↗ω = ↗v × (∇ × ↗v) = ÷12 ∇ v⁽2⁾ - (↗v⦁∇)↗v
  ```
  ∴
  ```
    (↗v⦁∇)↗v = ÷12∇v⁽2⁾ - ↗v × ↗ω
  ```
  substitute this into the euler equation:
  ```
    𝝏₍t₎↗v + ∇(÷12v⁽2⁾ + φ) + ÷1ρ∇p - ↗v×↗ω = 0
  ```
  (general form of bernoulli's law). {{< 𝖗 TB p698 >}}

¶ the fluid is ideal, so you ignore dissipation. thorne says p698 that this 
  means the entropy is constant along the flow, 
  ```
    Ɗ₍t₎s = (↗v⦁∇)↗s = 0
  ```
  - >> ? <<

  since the flow is steady, ˝𝝏₍t₎(all  variables) = 0˝, you can use the enthalpy 
  thermodynamic identity
  ```
    dh = Tds + ÷1ρ dp
  ```
  since ˝Ɗ₍t₎s = 0˝, this means
  ```
    (↗v⦁∇)p = ρ(↗v⦁∇)h
  ```

¶ dot ˝↗v˝ into the general B. equation, you get
  ```
    (↗v⦁∇) (÷12 v⁽2⁾ + φ) + ÷1ρ (↗v⦁∇p) - ↗v⦁(↗v×↗ω) = 0
  ```
  use eq (9), 

  ```
    (↗v⦁∇) (÷12 v⁽2⁾ + φ) + ρ(↗v⦁∇)h - (↗v⦁∇)(↗v⦁∇) + (↗v⦁∇)(÷12∇v⁽2⁾) = 0
  ```

¶ *define* {{< ℑ BERNOULLI FUNCTION >}}
  ```
    B = ÷12 v⁽2⁾ + h + Φ
  ```

¶ then you can write
  ```
    Ɗ₍t₎B = (↗v⦁∇)B = 0
  ```
  - so: for an ideal fluid, in a steady flow, the bernoulli function is 
    conserved.

  note
  ```
    B = ÷12 v⁽2⁾ + h + Φ = ÷12 v⁽2⁾ + u + ÷Pρ + Φ
  ```
  - the fluid's total energy density (KE + PE + internal) per unit mass PLUS the 
    work P(1/ρ) needed to inject a mass of fluid, volume 1/ρ, into a surrounding 
    fluid with pressure P.
  - enthalpy h = u + P/ρ is the injection energy per unit mass when there's no 
    KE and PE.

¶ in an isentropic+irrotational flow (vorticity vanishes), ˝↗ω = ∇×↗v = 0˝ , so 
  you introduce a velocity potential ˝ψ(↗x,t)˝, where
  ```
    ↗v = ∇ψ   (irrotational  flow)
  ```

  1st law of thermo: ˝∇h = T∇s + ÷1ρ∇p˝. in an isentropic flow this reduces to
  ```
    ∇p = ρ∇h
  ```

  and you end up getting
  ```
    ∇(𝝏₍t₎ψ + B) = 0
  ```
  - the qty in the brackets is constant everywhere.

  expanding
  ```
    ∇(𝝏₍t₎ψ + ÷12v⁽2⁾ + h + φ) = 0
  ```

  replace ˝∇h = ÷1ρ∇p˝
