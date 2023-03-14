---
title: "hydrodynamics"
type: long
---

# HYDRODYNAMICS
--------------------------------------------------------------------------------

¶ hydrodynamics is when the fluid velocity ˝↗v(↗x,t)˝ is nonzero (as opposed to 
  hydrostatics).

# CONSERVATION
--------------------------------------------------------------------------------

## conservation of mass, eulerian
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
    𝝏₍t₎ ∫₍V'₎ ρ dV
    == -∫₍V'₎ ∇⦁(ρ↗v) dV
    == -∫₍S₎ ρ↗v⦁d↗S
  {{< /M >}}
  - this is an application of gauss' law
  - S is the closed surface that bounds ˝V'˝
  - LHS: the rate of change of mass in volume ˝V'˝
  - RHS: the rate at which mass flows into ˝V'˝ through surface ˝𝝏S˝
  - ˝ρ↗v˝ is the mass flux
  - ˝-d↗S˝ is the inward facing surface element


## conservation of mass, lagrangian
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
  - >> physical interpretation? where else does this show up? is it a tenet of 
    continua? <<
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
  - >> what makes this a "lagrangian" formulation? <<

¶ define a fluid's **rate of expansion**, ˝θ˝, 
  ```
    θ = ∇⦁↗v = Ɗ₍t₎Θ
  ```

## conservation of momentum
-----------------------------

¶ for momentum conservation, the equation should be of form ˝𝝏₍t₎˝(momentum 
  density)+ ˝∇⦁˝(momentum flux) = 0

¶ for fluids the momentum density is ˝ρv˝.

¶ the momentum flux is (generally) the stress tensor ˝T˝

¶ momentum conservation, eulerian (differential conservation law)
  ```
    𝝏₍t₎(ρ↗v) + ∇⦁T = 0
  ```

# MECHANICAL STRESS TENSOR
--------------------------------------------------------------------------------

¶ building the mechanical stress tensor in a fluid: momentum flows through a 
  surface element d↗A, back to front.
  - see note on constructing the mechanical stress tensor [insert link]

¶ mechanical stress tensor ˝T₍m₎˝. flow of mechanical momentum.
  - >> what is mechanical momentum? <<

# IDEAL FLUIDS
--------------------------------------------------------------------------------

¶ an ideal fluid: one where you ignore dissipative processes like viscosity and 
  thermal conductivity.

¶ in an ideal fluid, the mass conservation law becomes ˝∇⦁↗v = 0˝, aka the 
  incompressible approximation.

¶ the momentum conservation law is
  ```
    𝝏₍t₎(ρ↗v) + ∇⦁T = ρ↗g
  ```
  [thorne p696]

# LAGRANGIAN MOMENTUM CONSERVATION
--------------------------------------------------------------------------------

¶ ˝↗f˝ is the netforce per unit volume on the fluid. then you can write momentum 
  conservation as
  ```
    𝝏₍t₎(ρ↗v) + ∇⦁T₍m₎ = ↗f
  ```
  insert ˝T = ρ↗v⊗↗v˝, you get the {{< ℑ LAGRANGIAN LAW OF MASS CONSERVATION >}}
  ```
    ρ·d₍t₎↗v = ↗f
  ```
  - d is the advective derivative, ˝d₍t₎ = 𝝏₍t₎ + ↗v⦁∇˝
  - this is F = ma per volume

  we want to make this equivalent to the eulerian conservation law, 
  ```
    𝝏₍t₎(ρ↗v) + ∇⦁T = 0
  ```
  there must be a stress tensor ˝T₍f₎˝ s.t.
  ```
    ↗f = -∇⦁T₍f₎
    T = T₍m₎ + T₍f₎
  ```

# MASS CONSERVATION
--------------------------------------------------------------------------------

¶ mass conservation can take the eulerian form
  ```
    𝝏₍t₎ρ + ∇⦁(ρ↗v) = 0
  ```
  or the lagrangian form
  ```
    d₍t₎ρ = -ρ∇⦁↗v
  ```

¶ so you need knowledge of a stress tensor ˝T₍f₎˝ for some material. if you know 
  the stress tensor ˝T₍f₎˝ for some material, then you know the force density 
  ˝↗f˝ that acts on the material.

  it's easier to determine the form of the stress tensor than the form of the 
  force.

# MOMENTUM CONSERVATION
--------------------------------------------------------------------------------

¶ in an ideal fluid, the only forces are gravity and the isotropic pressure P.

¶ momentum conservation:
  ```
    𝝏₍t₎(ρ↗v) + ∇⦁T = ρ↗g
  ```
  or
  ```
    𝝏₍t₎(ρ↗v) + ∇⦁(ρ↗v⊗↗v + P↗g) = ρ↗g
  ```
  where
  ```
    T = ρ↗v⊗↗v + P↗g      (ideal)
  ```

# THE INCOMPRESSIBLE APPROXIMATION
--------------------------------------------------------------------------------

¶ if you assume density is constant, you're saying the fluid is incompressible 
  (pq to compress the fluid, you have to induce some kind of density variation)

¶ incompressible fluid: you're assuming variations of pressure are so small that 
  changes in density are negligible

¶ when the approximation of constant ˝ρ˝ is valid:
  - if the velocities of the flow are much less than the speed of sound in the 
    fluid, you don't have to worry about density variations

# THE EQUATION OF STATE
--------------------------------------------------------------------------------

¶ need to establish the relations between variables.

¶ the theory of fluids starts with an equation of state. this eos relates the 
  pressure to the density. in the incompressible approximation, 
  ```
    ρ = const
  ```

¶ next relation: the conservation of matter. if matter flows away from a point, 
  then the amount of matter remaining must decrease. 
  - if the fluid velocity is ˝v˝, the mass that flows in a unit time across a 
    unit area is ˝ρv˝ (normal to the surface). this is a kind of mass flux.
  - in E&M, the divergence of flux gives the rate of decrease of density per 
    unit time.
  - here, 
  ```
    ∇⦁(ρv) = -𝝏{t}{ρ}
  ```
  - this is the __hydrodynamic continuity equation__. it expresses conservation 
    of mass for a fluid.
  - in the incompressible fluid approximation, the continuity equation reduces 
    to
  ```
    ∇⦁v = 0
  ```
  - ie the fluid velocity, ˝v˝, has zero divergence. like the magnetic field.

¶ relation from newton's law:
  - define ˝f˝, force per unit volume, aka __force density__, a vector qty
  ```
    ρ×(acceleration) = f
  ```
  - force density is a sum of three terms:
    - pressure force per unit volume, ˝-∇p˝
    - external force that act at a distance, like gravity or electricity. if 
      these external forces are conservative, with a potential per unit mass 
      ˝φ˝, they give a force density ˝-ρ∇φ˝
    - if these external forces are not conservative, you write ˝f₍ext₎˝, the 
      external force per unit volume
    - there's also an _internal_ force per unit volume. in a flowing fluid there 
      can also be a shearing stress. this is called the viscous force, ˝f₍visc₎˝
  ```
    ρ×(acceleration) = -∇p - ρ∇φ + f₍visc₎
  ```

¶ what happens when you drop the viscosity term
  - when you omit ˝f₍visc₎˝, it's like modelling a "thin" liquid
  - this is very much an approximation. in fact, this is a highly idealised model 
    of a liquid which is nothing like real fluids. 
  - the viscous term is an essential property of the fluid
  - historical note: john von neumann. he knew about the massive difference 
    between what happens when you don't include the viscous term. in the 
    development of hydrodynamics until 1900, the main interest was solving 
    beautiful mathematical problems using this approximation. had pretty much 
    nothing to do with real fluids. 
    - coined the term __dry water__

¶ so anyway, when you resolve all the forces and do a bunch of vectoring shiz, 
  the equation you end up getting is
  ```
    𝝏{t}{↗v} + (↗v⦁∇)↗v = -÷{∇p}{ρ} - ∇φ
  ```
  - or (our form)
  ```
    𝝏{t}{↗v} + (↗v⦁∇)↗v = -∇p + μ∇⁽2⁾↗v
  ```

# VORTICITY
--------------------------------------------------------------------------------

¶ define vorticity, ˝↗Ω˝, the curl of the velocity field ˝↗v˝
  ```
    ↗Ω = ∇×↗v
  ```
  - this is also a vector field

¶ what vorticity actually is:
  - take a small fluid element. 
  - consider how this fluid element moves over a short period of time ˝dt˝
  - each "bit" of fluid in the fluid element has a small displacement in this 
    interval. let the displacement of this bit be ˝↗ε = ↗vdt˝
  - the gradient of the displacement ˝↗ε˝ will be comprised of an expansion, 
    rotation, and shear.
  - the "vectorial" angle of rotation is ˝↗φ = ÷12·∇×↗ε˝
  - the time derivative of the vectorial angle of rotation is 
    ```
      Ɗ₍t₎↗φ = ÷12·Ɗ₍t₎↗ε = ÷12·∇×↗v
    ```
  - this is just the fluid element's rotational angular velocity
  - thus, the vortivity is just twice the angular velocity of rotation of a 
    fluid element.

¶ the equation of motion becomes
  ```
    𝝏{t}{↗v} + ↗Ω×↗v + ÷12 ∇v⁽2⁾ = -÷1ρ ∇p - ∇φ
  ```

¶ if vorticity is zero everywhere, the flow is __irrotational__
  - recall: the circulation of a vector field around any closed loop
  - the circulation around a closed loop in a fluid is the line integral of the 
    fluid velocity at a particular instant of time around that loop
  ```
    (circulation) = ∮ ↗v⦁d↗s
  ```

# VISCOSITY
--------------------------------------------------------------------------------

