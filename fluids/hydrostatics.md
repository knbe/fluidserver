---
time: 
title: hydrostatics
type: note
---

# STRESS, σ
--------------------------------------------------------------------------------

¶ is a quantity that describes the forces in an object that cause deformation 
  (strain). describes the internal forces that neighbouring particles exert on 
  each other, in a continuous material.

¶ defined as force per unit area.

¶ compressive stress: is when forces (like tension or compression) cause an 
  object to become compressed.
  - the bigger these forces and the smaller the cross sectional area, the 
    greater the stress.
  - is why stress is defined as force per unit area

¶ dimensions: ˝[σ] = L⁽-1⁾ M T⁽-2⁾˝

¶ SI unit: pascal
  - base units: ˝Pa = kg m⁽-1⁾ s⁽-2⁾˝

¶ [examples][1] of mechanical stress:
  - tension
  - compression
  - shear
  - bending
  - torsion

[1]: https://en.wikipedia.org/wiki/Stress_(mechanics)#/media/File:Different-types-of-mechanical-stress_EN.svg

# STRAIN, DEFORMATION
--------------------------------------------------------------------------------

¶ strain is a measure of deformation of an object. it describes the displacement 
  between particles relative to a reference length

¶ functional form of deformation:
  ```
    ↗x = F(↗x')
  ```
  - ↗x' is an array of reference positions for points of the body
  - deformations have units of length

¶ strains are usually dimensionless

¶ whenever a solid material undergoas a strain (deformation), there is an 
  internal elastic stress that causes the object to restore to its original 
  non-deformed state (like the spring force)

¶ in liquids and gases, ONLY deformations that change the volume will generate a 
  persistent elastic stress
  - if the deformation changes gradually, in fluids there will be some viscous 
    stress that opposes the change.

¶ elastic and viscous stresses are both kinds of mechanical stress.

# SHEAR FORCE AND SHEAR STRESS
--------------------------------------------------------------------------------

{{< 𝖉𝖊𝖋 SHEAR FORCES >}}
  forces that acts on one part of a body in a certain direction, and another 
  part in the opposite direction
{{< /𝖉𝖊𝖋 >}}

¶ if the forces are aligned (collinear), then they are just tension or 
  compression forces

{{< 𝖉𝖊𝖋 SHEAR STRESS τ >}}
  the component of stress that's coplanar with the body's cross section
  ```
    τ = ÷FA
  ```
  - ˝A˝ is the cross sectional area of the material that's parallel to the 
    applied force
  - points are coplanar if there's a plane that contains them all
{{< /𝖉𝖊𝖋 >}}

{{< fig shearstress.png 8 >}}

# WHAT DISTINGUISHES A FLUID
--------------------------------------------------------------------------------

¶ the main difference between a fluid and solid: a fluid can't maintain a shear 
  stress for any length of time. 
  - ie if you apply a shear to a fluid, it'll move
  - some fluids move more easily under shear than others

¶ viscosity: property that describes how easily a fluid yields (under a shear 
  stress)

# HYDROSTATICS: FLUIDS AT REST
--------------------------------------------------------------------------------

{{< 𝖉𝖊𝖋 HYDROSTATICS >}}
  the theory of liquids at rest.
{{< /𝖉𝖊𝖋 >}}

¶ in hydrostatics, ignore viscous effects.

¶ when liquids are at rest, there are no shear forces.

¶ basic law of hydrostatics: stresses are always normal to any surface inside 
  the fluid.

¶ pressure is the same in all directions.
  - for a given (arbitrary) surface in the fluid, the normal force on that 
    surface per area is the pressure. 
  - the pressure stress must be the same in all directions because there is no 
    shear on any plane in a static fluid (should prove this)

# PRESSURE VARIES WITH HEIGHT
--------------------------------------------------------------------------------

¶ in a static fluid on the earth's surface, pressure varies with height, because 
  of the weight of the fluid.
  - assume density ˝ρ˝ is constant
  - let the pressure at some arbitrary reference level be ˝p₍0₎˝
  - the pressure at height ˝h˝ above the reference point is:
    ```
      p = p₍0₎ - ρgh
    ```

¶ the quantity ˝p + ρgh˝ is a constant in a static fluid.

# PRESSURE ON A SMALL CUBE OF WATER
--------------------------------------------------------------------------------

what is the net force on the cube of water from the pressure?

¶ note:
  - pressure is the same in all directions in a static fluid
  - thus the only way there can be a net force per volume on the cube is because 
    the pressure changes from one point to another

{{< fig pressureoncubewater.jpg 8 >}}

¶ suppose there's some external force that can be described by a potential field 
  (like gravity). 
  - let ˝φ˝ be the potential energy per unit mass
  - the force per unit mass (for the potential field) is ˝-∇φ˝ 
  - if ˝ρ˝ is the fluid density, then the force per unit volume is ˝-ρ∇φ˝
  - since the system is in equilibrium, the force per unit volume for the 
    potential field must cancel the pressure force per unit volume, ie when you 
    add them they must be zero, so ˝-∇p - ρ∇φ = 0˝
  - this is the equation of hydrostatics

# EQUATION OF HYDROSTATIC EQUILIBRIUM
--------------------------------------------------------------------------------

¶ here:
  ```
    -∇p - ρ∇φ = 0
  ```
  - in general it has no solution
  - if the density varies arbitrarily, there's no way for the forces to balance, 
    and the fluid can't be in static equilibrium. convection currents will 
    start.
  - lookie here: the pressure term is a "pure" gradient. the other term has the 
    ˝ρ˝ prefactor. if it's a variable, this term _isn't_ a "pure" gradient. 
  - only when ˝ρ˝ is constant will the second term be a pure gradient.
  - then the equation has a solution
  ```
    p + ρφ = const
  ```
  - alternatively, ˝ρ˝ could also be a function of ˝p˝. this scenario also gives 
    hydrostatic equilibrium, and the equation will have a solution.

¶ another (thorne's) formulation of this: for a fluid at rest in a gravitational 
  field ˝↗g˝, the equation of hydrostatic equilibrium is the same as that for 
  (elastostatic) equilibrium with a vanishing shear stress, so
  ```
    T = P↗g
  ```
  and
  ```
    ∇⦁T = ∇P = ρ↗g
  ```
  
  you can express ˝↗g˝ as a potential: ˝↗g = -∇φ˝. and then you get feynman's 
  form.
