---
title: "conservation laws"
type: long 
---

# conservation of mass, eulerian
----------------------------------

¶ in the eulerian approach to mass conservation, you monitor the change in 
  density at a given point in space, rather than moving with the flow [thorne 
  p692]. 

¶ when dealing with continua, all conservation of mass laws tend to have the 
  form ˝𝝏₍t₎˝(density of something) = ˝∇⦁˝(flux of that thing). ie, rate of 
  change of density wrt time = rate of change of flux wrt space


¶ conservation of mass, differential form:
  ```
    𝝏₍t₎ρ + ∇⦁(ρ↗v) = 0     𝓮𝓺{221}
  ```

¶ any "newtonian" conservation law in differential form has a corresponding 
  _integral_ form [thorne p692]. you have to integrate the differential law over 
  some arbitrary volume, call it ˝V'˝
  {{< M >}}
    𝝏₍t₎ ∫₍V'₎ ρ dV == -∫₍V'₎ ∇⦁(ρ↗v) dV
    == -∫₍S₎ ρ↗v⦁d↗S
  {{< /M >}}
  - this is an application of gauss' law
  - S is the closed surface that bounds ˝V'˝
  - LHS: the rate of change of mass in volume ˝V'˝
  - RHS: the rate at which mass flows into ˝V'˝ through surface ˝𝝏S˝
  - ˝ρ↗v˝ is the mass flux
  - ˝-d↗S˝ is the inward facing surface element


# conservation of mass, lagrangian
------------------------------------

¶ in the lagrangian approach to mass conservation, you look at the change in 
  density as an observer who moves with the flow ˝↗v˝ [thorne p692]

¶ mass conservation, differential form, lagrangian:
  ```
    Ɗ₍t₎ρ = -ρ ∇⦁↗v
  ```
  - ˝Ɗ₍t₎˝ is the advective time derivative, ˝Ɗ₍t₎ = 𝝏₍t₎ + ↗v⦁∇˝
  - derivation: expand the second term in \eqref{221}, 
    ```
      ∇⦁(ρ↗v) = (∇ρ)⦁↗v + ρ∇⦁↗v
    ```
    ∴
    {{< M >}}
      Ɗ₍t₎ρ 
      == 𝝏₍t₎ρ + ↗v⦁(∇ρ)
      == -(∇ρ)⦁↗v - ρ∇⦁↗v + ↗v⦁(∇ρ)
    {{< /M >}}
    the first and last terms cancel, so
    ```
      Ɗ₍t₎ρ = -ρ∇⦁↗v    𝓮𝓺{222}
    ```

¶ ˝Ɗ₍t₎˝, the **advective time derivative**,
  ```
    Ɗ₍t₎ = 𝝏₍t₎ + ↗v⦁∇
  ```
  - physical interpretation?
  - note, the partial derivative ˝𝝏₍t₎˝ is the rate of change of something 
    (XXX), wrt time, at a fixed point in space, ie you could express it more 
    formally as ˝𝝏₍t₎ = 𝝏₍t₎|₍↗x₎˝
  - so, for a system in motion (a system changing with time), the partial 
    derivative ˝𝝏₍t₎˝ compares the qty XXX at two _different points in the 
    flow_, but at the _same point in space_. it compares qty XXX at location 
    ˝↗x˝ at time ˝t˝ to qty  XXX at location ˝↗x˝ at time ˝t + dt˝.
  - the advective derivative follows the motion. it compares XXX at two 
    different times, at the _same point in the material_

¶ how the lagrangian approach works:
  - consider an block of fluid, volume ˝V˝
  - the mass in the block of fluid is ˝m = ρV˝
  - as the fluid flows, the mass must be conserved, so
    ```
      Ɗ₍t₎m = (Ɗ₍t₎ρ)·V + ρ·(Ɗ₍t₎V) = 0
    ```
    or
    ```
      Ɗ₍t₎ρ = -÷ρV·Ɗ₍t₎V
    ```
  - now compare this with \eqref{222}, since ˝Ɗ₍t₎ρ = -ρ∇⦁↗v˝, 
    ```
      ∇⦁↗v = ÷1V Ɗ₍t₎V
    ```
  - so the divergence of the flow velocity ˝↗v˝ is the rate of change of the 
    fluid block's volume divided by ˝V˝ (thorne calls this the "fractional rate 
    of increase of the fluid block's volume)

¶ define a fluid's **rate of expansion**, ˝θ˝, 
  ```
    θ = ∇⦁↗v = Ɗ₍t₎Θ
  ```

# conservation of momentum
-----------------------------

¶ for momentum conservation, the equation should be of form ˝𝝏₍t₎˝(momentum 
  density)+ ˝∇⦁˝(momentum flux) = 0

¶ for fluids the momentum density is ˝ρv˝.

¶ the momentum flux is (generally) the stress tensor ˝T˝

¶ momentum conservation, eulerian
  ```
    𝝏₍t₎(ρ↗v) + ∇⦁T = 0
  ```

