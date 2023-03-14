---
title: "modified porous medium equation"
type: long
---

# INTRO
--------------------------------------------------------------------------------

¶ you can't always get similarity solutions using dimensional analysis, because 
  ADs can occur.

¶ goal:
  - show an example of this (how you can't always get SSs using DA) by looking 
    at the LT bhvr of a slight modification to the diffusion equation
  - will show that a naive application of DA fails to get the correct LT bhvr, 
    BUT a modded similarity solution with an AD _does_ get the correct LT bhvr

¶ order:
  - postulate the form of the similarity solution
  - determine the AD by requiring that the postulated form satisfy the BCs of 
    the problem
  - then you can do the same problem using RG

# THE MODIFIED POROUS MEDIUM EQUATION
--------------------------------------------------------------------------------

¶ setup: a porous medium, on top of an impermeable horizontal layer. 
  - in the porous medium is a groundwater mound.
  - ?? ok, I mean, wtf is a groundwater mound? let's break this down. 
    groundwater is the water in rock and soil pores in the earth's surface. a 
    mound is a heaped pile of shiz. typically soil, debris, earth, etc. but I 
    guess in this case, water. how can you have a "heap" of water? isn't it 
    going to relax and spread out? ok, maybe that's why this is in the FFE 
    section. the mound doesn't stay still. maybe.
  - inside the mound, the pores of rock are partially filled with water.
  - outside the mound, the pores are empty of water but filled with gas.
  - the mound is unstable (pq the earth's gravitational field). 
  - it settles by spreading parallel to the plane of the impermeable layer.

¶ goal: to describe the approach to the equilibrium state (where the groundwater 
  mound is completely flat). 

¶ the dynamics of the settling of the mound can be described with a PDE for the 
  time evolution of the height ˝h˝ of the mound above the impermeable layer.

¶ treat the mound as axisymmetric, so height is a function of the radial 
  coordinate ˝r˝ in the ˝xy˝ plane, and time ˝t˝.
  - axisymmetric flow: one where the flow variables don't vary with (depend on) 
    the angular coordinate ˝θ˝. [link][1]

[1]: https://www.sciencedirect.com/topics/engineering/axisymmetric-flow

¶ assume the flow is slow.

¶ under these conditions, two valid approximations:

¶ approximation 1: the pressure in the groundwater mound is given by the 
  [hydrostatic pressure][2]
  ```
    p(r,z,t) = ρg(h(r,t) - z)
  ```
  - in a fluid at rest, all frictional and inertial stresses are zero. in these 
    conditions, the state of stress is hydrostatic.
  - in a [barotropic fluid][3] in a conservative force field (like gravity), the 
    pressure exerted by the fluid at equilibrium is a function of force exerted 
    by gravity

  {{< fig hydrostaticpressure.jpg 8 >}}

  - now, assume the fluid is incompressible, ie constant density, 
  - also, since the height ˝h˝ of the fluid column between ˝z˝ and ˝z₍0₎˝ is 
    small compared to the radius of the earth, assume ˝g˝ is constant
  - then the integral becomes
  ```
    p - p₍0₎ = ρgh
  ```

[2]: https://en.wikipedia.org/wiki/Hydrostatics#Hydrostatic_pressure
[3]: https://en.wikipedia.org/wiki/Barotropic_fluid

¶ approximation 2: the flux ˝j˝ of groundwater is proportional to the gradient 
  of the pressure head ˝p + ρgz˝. this is [d'arcy's law][4]
  ```
    j = -÷κμ 𝝏{r}{ρgh}
  ```
  - ˝κ˝ is the permeability
  - ˝μ˝ is the viscosity of the groundwater
  - more generally, in 3d, in isotropic porous media, 
  ```
    ↗j = -÷κμ·∇p
  ```
  - [read][5]

[4]: https://en.wikipedia.org/wiki/Darcy's_law
[5]: https://en.wikipedia.org/wiki/Darcy's_law#Derivation

¶ now describe the physics of transporting groundwater into and out of the pores 
  in the rock:
  - a given volume of rock can't be completely occupied by fluid. only the pores 
    can be filled.
  - the fraction of pores is the **porosity** ˝m˝, normally about ˝÷{1}{10}˝
  - when groundwater occupies a pore, only a fraction ˝σ˝ is occupied, and the 
    rest is filled with gas
  - when groundwater leaves a pore, a thin wetting layer remains on the walls of 
    the pore, so a fraction ˝σ₍0₎˝ of the pore remains filled with groundwater
  - assume the pores are in one of these two states only. call them occupied 
    (when a fraction ˝σ˝ of the pore is filled) or unoccupied (when a fraction 
    ˝σ₍0₎˝ is filled)
  - note there's an asymmetry in the dynamics: the rate at which empty pores 
    are filling with groundwater is not the same as the rate at which  
    occupied pores are losing groundwater
  - there's a time-dependent radius ˝r₍0₎(t)˝, where for ˝r > r₍0₎(t)˝, 
    previously unoccupied pores are becoming occupied, and for ˝r < r₍0₎(t)˝, 
    previously occupied pores are becoming depleted
  - ie inside the region (enclosed by the radius), ˝𝝏{t}{u} < 0˝ (density is 
    decreasing with time) and outside the region, ˝𝝏{t}{u} > 0˝ (density 
    increasing with time)

  {{< fig groundwatermound.png 8 >}}

¶ derive the equation of motion for ˝h˝
  - consider the conservation of water in a shell of radius ˝r˝, height ˝h˝, 
    thickness ˝dr˝

# MATHEMATICAL FORMULATION
--------------------------------------------------------------------------------

¶ the problem: consider a porous medium (literally a material with pores). 
  ordinarily the pores are filled with gas. suppose the porous medium is sitting 
  on top of an impermeable region. imagine there's a groundwater mound in the 
  porous region (a region where the pores are filled with groundwater, not gas).

  {{< fig porousmedium.jpg 8 >}}

  assume the mound is axially symmetric.

  under gravity the mound spreads out. eventually the mound will lie flat along 
  the bottom impermeable layer.

  ˝h˝ is the height of the mound. let ˝h = h(r,t)˝, so ˝h˝ is a function of 
  radial distance ˝r˝ (in the horizontal direction, ie the direction 
  perpendicular to gravity) and time ˝t˝. 

  assume the height of the mound ˝h(r,t)˝ decreases with increasing ˝r˝. 
  obviously, ˝r˝ increases with time.

¶ assume the fluid motion is slow, so the water pressure in the mound obeys the 
  equation for hydrostatic pressure:
  ```
    p = ρg(h-z)
  ```
  - ˝ρ˝ is the groundwater density
  - ˝g˝ is the acceleration due to gravity

  the total head (pressure head) is the quantity ˝p + ρgz˝. this quantity is 
  constant everywhere in the mound, equal to ˝ρgh˝

¶ the physical mechanism for how water enters/exits the pores: use the darcy 
  law. common for filtration problems.

  darcy's law: the flux of fluid (flow rate per unit area per unit time) is 
  proportional to the gradient of the total head. in this case
  ```
    j = -÷κμ·𝝏{r}{(ρgh)}
  ```
  - ˝κ˝ is the permeability coefficient. a property of the porous medium. 
    dimensions of area. 
  - ˝μ˝ is the dynamic viscosity of the groundwater.

  the total flux of water through a cylindrical surface of area ˝2πrh˝ is (from 
  darcy's law)
  ```
    j = -÷κμ·𝝏{r}{(ρgh)}·2πrh
    == -÷κμ·ρg·(𝝏{r}{h})2πrh
    == -÷{κρgπ}{μ}·r·𝝏{r}{h⁽2⁾}
  ```
  - in the last step, note that 
  ```
    𝝏{r}{h⁽2⁾} = 2h·𝝏{r}{h}
  ```

  {{< fig porousmedium2.jpg 8 >}}

¶ the __porosity__ of the medium is the fraction of the rock occupied by pores 
  (and thus the fraction of the rock that can occpuy water), denoted ˝m˝, is 
  normally of the order ˝÷{1}{10}˝

  also, when water enters a pore, it doesn't occupy the entire volume, only a 
  fraction ˝σ˝, and the rest is gas.

  groundwater also doesn't completely leave a pore that's initially full. some 
  fraction of water remains in the pore (wetting, held back by capillary 
  forces). denote this fraction ˝σ₍0₎˝. 

  assume ˝m,σ,σ₍0₎˝ are constants.

¶ there is a value of ˝r˝, call it ˝r₍0₎˝, where the dynamics has an asymmetry. 
  for ˝r < r₍0₎˝ the water is leaving pores that were previously filled. and for 
  ˝r > r₍0₎˝ the water is filling pores that were previously empty.

  {{< fig porousmedium3.jpg 8 >}}

  ˝r₍0₎˝ is a function of time.

  when ˝r > r₍0₎(t)˝, ˝𝝏{t}{h} > 0˝, 

  when ˝ r < r₍0₎(t)˝, ˝𝝏{t}{h} < 0˝. 

  ie, the the mound height function ˝h(r,t) ˝is decreasing below ˝r₍0₎˝, and 
  increasing above. look at the picture.  it makes sense. 
  - eureka: to be clear, ˝h˝ is not the height of the highest part of the mound, 
    as you previously thought. ˝h˝ is a function or ˝r,t˝, it's literally the 
    curve that describes the boundary of the mound. 

  the derivative ˝𝝏{t}{h}˝ vanishes at the radius ˝r = r₍0₎˝.

¶ now you need to derive the equation of motion for the mound height ˝h˝. as 
  mentioned above, there's an asymmetry in the dynamics at radius ˝r₍0₎˝. you 
  need to treat cases ˝r < r₍0₎˝ and ˝r > r₍0₎˝ separately.

  first, for both cases, you need to find the rate of change of volume of water in a 
  "shell". just to clarify, the mound is a 3d thing. here it is

  {{< fig hequation.jpg 8 >}}

  and here's a cross section, with this so-called "shell" highlighted:

  {{< fig shellofmound.jpg 8 >}}

  so the shell volume element is the volume of the mound between two cylinders, 
  one with radius ˝r˝ and the other ˝r + dr˝. "shell". pay attention.

  the volume contained in this shell: I suppose, to be proper, you could do 
  ˝π(r+dr)⁽2⁾h - πr⁽2⁾h˝, but since the shell thickness is infinitesimal, you 
  can just do area times length, the area being the SA of the inner cylinder, 
  ˝2πrh˝, and the length being ˝dr˝. so the volume of the porous medium 
  contained in this shell is
  ```
    V₍sh₎ = 2πrh·ɗr
  ```

  the volume of _fluid_ contained in ˝V₍shell₎˝ at time ˝t˝ is
  ```
    V₍sh,fl₎ = mσ·2πrh·ɗr
  ```
  - ˝m˝ is the porosity, the fraction of the medium that is pores, ˝σ˝ is the 
    fraction of each pore that can actually be occupied by water.
  - here ˝h = h(r,t)˝, ie the value of ˝h˝ at radius ˝r˝ and time ˝t˝

  now, you need an expression for the rate of change of ˝V₍sh,fl₎˝. when ˝t → 
  t+dt˝, the variable that changes in ˝V₍sh,fl₎˝ is ˝h˝, since ˝h = h(r,t)˝. 
  
  when ˝r > r₍0₎˝, the volume of water in the shell at time ˝t + dt˝ is
  ```
    V₍sh,fl₎(r > r₍0₎, t = t + dt) = mσ·2πr·h(r,t+dt)·ɗr
  ```
  
  so the rate of change of ˝V₍sh,fl₎˝ when ˝r > r₍0₎˝ is
  ```
    𝝏{t}{V₍sh,fl₎|₍r > r₍0₎₎} = mσ2πr·𝝏{t}{h}·ɗr
  ```

  when ˝r < r₍0₎˝, the volume of water in the shell at time ˝t + dt˝ is
  ```
    V₍sh,fl₎(r < r₍0₎, t = t + dt) 
    = mσ·2πr·h(r,t+dt)·ɗr + mσ₍0₎·2πr·(h(r,t) - h(r,t+dt))·ɗr
  ```

  so the rate of change of ˝V₍sh,fl₎˝ when ˝r < r₍0₎˝ is
  ```
    𝝏{t}{V₍sh,fl₎|₍r < r₍0₎₎} = m(σ - σ₍0₎)·2πr·𝝏{t}{h}·ɗr
  ```

  now, apply conservation (in this case conservation of water). ˝V₍sh,fl₎|₍r < 
  r₍0₎₎˝ should be equal to the rate of change of volume of water due to the 
  decrease of water saturation from ˝σ˝ to ˝σ₍0₎˝.

  darcy's law says ˝j = -(κ/μ)·𝝏{r}{(ρgh)}˝. to be clear, this is the flux of 
  groundwater per unit area per unit time. the flux through an area ˝2πrh˝ is
  ```
    -÷κμ·𝝏{r}{(ρgh)}·2πrh
  ```
  - I have trouble with this, because the definition of darcy's law (on 
    wikipedia anyway) incidates the pressure gradient is in the same direction 
    as the flow, but here we're looking at a flow radially outwards, but the 
    pressure gradient is vertical. I'm assuming there's some kind of math thing 
    where in this special case they're actually the same, because the radial 
    outward flow is _caused_ by the vertical pressure drop, or something...

  anyway, so the _rate of change of_ flux through area ˝2πrh˝ (wrt radius) is 
  just
  ```
    ÷κμ·𝝏{r}{(𝝏{r}{(ρgh)}·2πrh)}
  ```

  to compare this to the rate of change of ˝V₍sh,fl₎˝, you need to convert this 
  into a volume, so just multiply by the length ˝dr˝ (now it's the volumetric 
  flux? I think?)
  ```
    ÷κμ·𝝏{r}{(𝝏{r}{(ρgh)}·2πrh)}·ɗr
  ```

  now, _both_ expressions for the rate of change of ˝V₍sh,fl₎˝ (for the two 
  cases above) should be equal to this.

  for ˝r > r₍0₎˝:
  ```
    mσ2πr·𝝏{t}{h}·ɗr = ÷κμ·𝝏{r}{(𝝏{r}{(ρgh)}·2πrh)}·ɗr
  ```
  for ˝r < r₍0₎˝:
  ```
    m(σ - σ₍0₎)·2πr·𝝏{t}{h}·ɗr = ÷κμ·𝝏{r}{(𝝏{r}{(ρgh)}·2πrh)}·ɗr
  ```

  so, at long fucking last, the PDE for the mound height function is
  ```
    𝝏{t}{h} 
    = ÷{κ₍1₎}{r}·𝝏{r}{(r·𝝏{r}{h⁽2⁾})}   for: 𝝏{t}{h} ≤ 0
    = ÷{κ₍2₎}{r}·𝝏{r}{(r·𝝏{r}{h⁽2⁾})}   for: 𝝏{t}{h} ≥ 0
    (*1)
  ```
  - where
  ```
    κ₍1₎ = ÷{κρg}{2mμ(σ - σ₍0₎)}
    κ₍2₎ = ÷{κρg}{2mμσ}
  ```

  in shorter form:
  ```
    𝝏{t}{h} = ÷Dr·𝝏{r}{(r·𝝏{r}{h⁽2⁾})}
  ```
  - where ˝D = κ₍1₎ for: 𝝏{t}{h} < 0˝ and ˝D = κ₍2₎ for: 𝝏{t}{h} > 0˝

¶ conditions for the solution for ˝h(r,t)˝. 

  well, ˝h˝ must be continuous (look at the mound. a discontinuous solution 
  wouldn't work).

  the flux of water ˝j˝, which is proportional to ˝𝝏{r}{h⁽2⁾} = 2h𝝏{r}{h}˝, must 
  be continuous. (again, think about what flux is).
  - this basically means the derivative ˝𝝏{r}{h}˝ must be continuous for nonzero 
    ˝h˝, but for ˝h = 0˝ the derivative may have a discontinuity, as long as 
    ˝𝝏{r}{h⁽2⁾}˝ is continuous.

¶ also need an initial condition for the PDE. assume at ˝t = 0˝ the water is 
  concentrated within a finite region of the medium. the saturation in the mound 
  is ˝σ˝ (no pores have gone through an emptying process), and the total volume 
  of water in the mound is ˝V₍mound,fl₎˝.
  
  the initial height distribution of the mound, ˝h(r,t = 0)˝ is of form
  ```
    h(r,t=0) = ÷{V₍mound,fl₎}{2πmσ·r₍init₎⁽2⁾}·h₍0₎(÷{r}{r₍init₎})
    (*2)
  ```
  - ˝r₍init₎˝ is the initial maximum radius of the mound
  - ˝h₍0₎(s)˝, where ˝s = r / r₍init₎˝, is a monotonic nonincreasing 
    dimensionless function defined so that ˝h₍0₎(s)˝ is zero for ˝s ≥ 1˝ and the 
    integral is equal to 1
  ```
    ∫{0}{1} ɗs s·h₍0₎(s) = 1
  ```

  this is a complete mathematical formulation of the groundwater mound problem. 
  we want a solution to the PDE (*1) that's continuous, has a continuous 
  derivative ˝𝝏{r}{h⁽2⁾}˝, and satisfies the  initial condition (*2)

# THE MODIFIED POROUS MEDIUM EQUATION
--------------------------------------------------------------------------------

¶ the PDE (*1) in cylindrical coordinates is a specific form of a more general 
  equation called the **modified porous medium equation**
  ```
    𝝏{t}{u(r,t)} = D·Δ₍d₎·u(r,t)⁽1+n⁾
  ```
  - ˝D˝ is a discontinuous function of ˝𝝏{t}{u}˝, similar to the one above.
  - ˝Δ₍d₎˝ is the laplacian operator in ˝d˝ dimensions.
  - the case ˝n = 0˝ describes an **elasto-plastic porous medium**, ie the 
    medium can expand and contract irreversibly in response to the fluid flow in 
    it. this is aka **barenblatt's equation**.
  - when ˝D˝ is constant (rather than discontinuous in ˝𝝏{t}{u}˝, it's called 
    the **porous medium equation**. it can model many nonequilibrium phenomena 
    in fluid dynamics, depending on the value of ˝n˝.
  - the form of ˝D˝ implies the equation is nonlinear. when ˝D˝ is constant, 
    barenblatt's equation reduces to the diffusion equation.

