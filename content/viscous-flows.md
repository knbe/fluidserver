---
title: "viscous flows"
type: long
---

# FLUID MOTION RECAP
--------------------------------------------------------------------------------

¶ the laws of motion for a fluid are contained in the equation
  ```
    𝝏{t}{↗v} + (↗v⦁∇)↗v = -÷1ρ·∇p - ∇φ + ÷1ρ·↗f₍visc₎
  ```

¶ in the dry water approximation you leave out the last term, ie neglect viscous 
  effects

¶ another (additional) approximation is assuming the fluid is incompressible, so
  ```
    ∇⦁↗v = 0
  ```

¶ the incompressible approximation is good when flow speeds are much slower than 
  the speed of sound. but in real fluids the dry water approximation is not a 
  good approximation at all. most of the interesting dynamics come from the 
  viscosity term
  - in dry water the circulation never changes. if circulation is zero at the 
    beginning, it will always be (the opposite of reality)


# VISCOSITY
--------------------------------------------------------------------------------

¶ to be clear, viscosity is a measure of the internal frictional force between 
  adjacent layers of a liquid that are in relative motion. in a viscous liquid, 
  flow near the centre of a pipe is faster than at the walls.
  - stress is needed to sustain a viscous flow. you need a force to overcome the 
    friction between layers of the fluid that are in relative motion.
  - for a tube with constant flow rate, the strength of the compensating force 
    is proportional to the fluid viscosity.

¶ viscosity of a newtonian fluid doesn't change much with rate of deformation.

¶ viscous stress tensor: a tensor to model the part of stress in a material 
  that's attributed to the strain rate, the rate at which it's deforming around 
  that point

¶ consider viscous drag between parallel plates. if you measure the force needed 
  to keep the upper plate moving, you'll find it's proportional to the area of 
  the plates and to ˝v₍0₎/d˝, where ˝d˝ is the distance between the plates
  - ie, the shear stress ˝F/A˝ is proportional to ˝v₍0₎/d˝
  ```
    ÷FA = μ·÷{v₍0₎}{d}
  ```
  - the constant of proportionality ˝μ˝ is the viscosity (coefficient of 
    viscosity)

# SHEAR, STRESS, DECOMPOSITION OF VELOCITY GRADIENT
--------------------------------------------------------------------------------

¶ some fluids develop a shear stress as they flow (eg honey), some can flow 
  freely (eg water)
  - reason: pretty much all flows are in contact with a solid body (like walls 
    of a pipe etc). this contact forms boundary layers. 
  - the thickness and behaviour of boundary layers are controlled by viscous 
    forces.
  - the boundary layers can then influence the bulk flow (in the bulk flow the 
    viscosity is negligible), eg by initiating turbulence in the bulk flow


¶ we have to mod the fluid dynamics equations ot include viscous stresses.

¶ decomposition of the velocity gradient tensor ˝∇↗v˝:
  - ˝θ˝, rate of expansion
  - ˝↗σ˝, rate of shear tensor (symmetric)
  - ˝↗r˝, rate of rotation tensor (antisymmetric)
  ```
    ∇↗v = ÷13 θ ↗g + ↗σ + ↗r
  ```
  - inverting this equation gives
  ```
    θ = ∇⦁↗v
    σ⟦ij⟧ = ÷12 (v⟦ij⟧ + v⟦ji⟧) - ÷13 θ g⟦ij⟧
    r⟦ij⟧ = ÷12 (v⟦ij⟧ - v⟦ji⟧) = -÷12 ε⟦ijk⟧ ω⁽k⁾
  ```
  - where ˝↗ω = 2d↗φ/dt˝ is the vorticity

# FLUIDS AND SHEAR STRESSES
--------------------------------------------------------------------------------

¶ a fluid at rest doesn't exert a shear stress. this is what distinguishes it 
  from an elastic fluid.

¶ a fluid in motion _can_ resist shear in the velocity field.

¶ the _magnitude_ of shear stress is linearly related to the velocity gradient. 
  - well, in most fluids anyway; this is an experimental result
  - discovered by newton (ie attributed to newton)
  - fluids that obey this law are **newtonian fluids**

¶ fluids are usually isotropic.
  - exception: liquid crystals, which are smectic.

# NAVIER STOKES EQATION
--------------------------------------------------------------------------------

¶ the linear relation between stress and rate of strain can be described by two 
  constants: the **bulk viscosity** ˝ζ˝ and the **shear viscosity** ˝η˝.

¶ the viscous contribution to the stress tensor:
  ```
    T₍vis₎ = -ζθg - 2ησ
  ```
  if you include this viscous contribution in the stress tensor, and make use of 
  momentum conservation,
  ```
    𝝏{t}{(ρ↗v)} + ∇⦁T = ρg    𝓮𝓺{1}
  ```
  you get:

¶ __navier stokes equation:__
  ```
    ρ Ɗ{t}{↗v} = -∇P + ρg + ∇(ζθ) + 2∇⦁(ησ)
  ```
  - the last two terms are the viscous force density
  - in incompressible flows, ˝θ˝ can be approximated as zero, and you can ignore 
    bulk viscosity.
  - the viscosity coefficient ˝η˝ varies much more slowly than the shear ˝σ˝. so 
    you can take it outside the divergence.
  - then you get:
  ```
    Ɗ{t}{↗v} = - ÷1ρ ∇P + g + ν∇⁽2⁾↗v
  ```
  - where the **kinematic viscosity**
  ```
    ν = ÷ηρ
  ```
  - ˝η˝ is the **dynamic viscosity**
  - this is the more common form of the NS equation

# VISCOSITY
--------------------------------------------------------------------------------

¶ microscopic difference between gases and liquids:
  - in a gas a molecule of mass ˝m˝ travels a distance that's of the order of 
    its mean free path, ˝λ˝, before it collides
  - if there's a shear in the fluid, then the molecule (travelling upwards in 
    the y direction, look at the diagram) will transfer momentum in the 
    x-direction around ˝-mλσ₍xy₎˝ between collisions

  {{< fig molecularOriginOfViscosity.png 6 >}}

  - if ilya ˝n˝ molecules per unit volume moving with mean thermal speeds 
    ˝v₍th₎˝, the transferred momentum crossing a unit area in unit time is
  ```
    T₍xy₎ ∼ -nm v₍th₎ λσ₍xy₎
  ```
  - compare to this to 𝓮𝓻{1}. you can estimate the coefficient of shear 
    viscosity:
  ```
    η ≃ ÷13 ρ v₍th₎ λ
  ```
  - in a gas, the mean thermal KE ˝÷32 ƙT˝ is ˝∼mv₍th₎⁽2⁾˝
  - ∴ the coeffcient of viscosity increases with temperature via ˝ν ∝ T⁽1/2⁾˝
