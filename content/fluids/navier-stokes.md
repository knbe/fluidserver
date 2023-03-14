---
title: "navier stokes"
type: long
---

¶ the navier stokes equations
  ```
    ∇⦁↗v = 0
    ρ·𝝏{t}{↗v} = -∇p + μ∇⁽2⁾↗v + ρF
  ```

¶ the conservation of mass equation
  ```
    ∇⦁↗v = 0
  ```
  - aka the incompressibility equation
  - expanded:
    ```
      (𝝏{x}{}↑x + 𝝏{y}{}↑y + 𝝏{z}{}↑z)⦁(v₍x₎↑x + v₍y₎↑y + v₍z₎↑z) = 0
      𝝏{x}{v₍x₎} + 𝝏{y}{v₍y₎} + 𝝏{z}{v₍z₎} = 0
    ```
  - all this equation says is, _mass is conserved_

¶ newton's 2nd law, mass × acceleration = force
  ```
    ρ·𝝏{t}{↗v} = -∇p + μ∇⁽2⁾↗v + ρF
  ```
  - the momentum equation
  - the first two terms are the internal forces, the force from all the 
    particles colliding with each other
  - the third term is the external force (normally this is just gravity, but you 
    can also add E&M effects (magnetohydrodynamics, is how stars/galaxies 
    form), coriolis, etc)
  - first term: pressure gradient (internal force)
    ```
      ∇p = 𝝏{x}{p} + 𝝏{y}{p} + 𝝏{z}{p}
    ```
    - when there's a difference in pressure between two regions, there's a 
      pressure gradient, which causes movement. the fluid will move along the 
      pressure gradient
  - second term: viscosity (internal force)
    - if you think of the fluid as a stack of layers
    - the layers slide past each other, and create a friction.
    - that friction is viscosity

¶ the NS equations have been around since the 1820s. anything modelling a fluid, 
  you start with the NS equations
  - but, we still don't really understand them mathematically

¶ when you have a set of equations, mathematically speaking, you want those 
  equations to satisfy three properties
  - the solution exists
  - the solution must be unique
  - the solution must be smooth, ie well behaved, ie if you make a small change 
    in how you start the experiment, you want to the result to also have a small 
    change

¶ in the NS equation, we don't know if a solution exists all the time
  - given an IC, a starting velocity and pressure, input it, don't know if a 
    solution will come out
  - since we don't know if a solution always exists, we find ways to cheat
  - we make simplifications, assumptions, to remove terms from the equation
  - another thing we do: averaging: rather than considering a velocity field 
    defined everywhere, you take a "circle" (region) of fluid, take the average 
    in that region, and now find out how _that_ changes, behaves, etc

¶ in 2D, solutions exist, and they are well behaved
  - but in 3D, nope
