---
time: 202304181310
title: "Flow past a Cylinder"
type: example2
source: 
---

Consider a cylinder placed perpendicular to a flow. Assume ˝⬀v˝ is small 
compared to the speed of sound, so you can ignore compressibility. Assume 
gravity is negligible. 

Parameters:
- ˝d˝, the diameter of the flow (and ∴ characteristic length scale of the 
  problem)
- ˝V˝, the velocity of the flow far before it reaches the cylinder ("upstream 
  velocity").
- ˝ρ˝, density
- ˝ν˝, kinematic viscosity

Reynolds number:
```
  Re = ÷1ν Vd
```

Note: if you had a flow where the sound speed ˝c₍s₎˝ is sufficiently high to to 
invalidateincompressibility, then you can define the mach number (another 
dimensionless number)
```
  M = ÷V{c₍s₎}
```

Initially the flow is stationary. The equations that describe the flow: 
```
  ∇⦁⬀v = 0
```
(incompressibility)
```
  (⬀v⦁∇)·⬀v = -÷1ρ ∇P + ν·∇⁽2⁾·⬀v 
```
(time indep. NS, since the flow is stationary and ˝𝝏₍t₎⬀v = 0˝).

There are four equations in total (3 components of NS + incompressibility). You 
can solve them for pressure ˝p˝ and velocity ˝⬀v˝ subject to the condition that 
˝⬀v = 0˝ on the surface and is uniform upstream.

The only dimensionless number is ˝Re˝, so the solution to the flow equations 
will have the form
```
  ÷1V ⬀v = ⬀U(÷1d ⬀x, Re)
```
  - ˝÷1d ⬀x˝ is dimensionless and Re is dimensionless, so ˝⬀U˝ is a 
    dimensionless function
  - this is a scaling relation. you can use it to determine similar solutions.  
    e.g. if you scale ˝V˝ and ˝d˝ by (˝×2˝), then to get a similar flow (same Re number, 
    ˝Re = ÷1ν Vd˝) you need to scale ˝ν˝ by (˝×4˝) to get a similar solution.
