---
title: incompressible flows
type: note
---

¶ *define* {{< ℑ INCOMPRESSIBLE FLOW >}} : a flow where the density is constant 
  in a parcel of fluid. incompressible flows obey:
  ```
    ∇⦁↗v = 0
  ```
  ˝↗v˝ is the flow velocity (a vector field since it's a flow).

  note this equation has the same form as the equation for a solenoidal field. 
  indeed, for incompressible flows the velocity field is solenoidal.

¶ when can you assume the fluid density is constant? well, if the flow velocity 
  is much smaller than the speed of sound ("highly subsonic flow") && gravity 
  isn't strong enough to compress the fluid significantly, then changes in fluid 
  density are negligible. the incompressible flow equation is an assumption 
  only. {{< 𝖗 TB p676 >}}

  consider a flow, with variables ˝P, v, ρ, ...˝. 
  - let ˝L˝ be the characteristic length over which these variables vary. (just 
    a pretentious way of saying, the kind of lengths where you can measure and 
    observe differences in these variables. e.g. macroscopic... the "human" 
    scale? is one example)
  - let ˝T˝ be the characteristic timescale over which the variables vary.
  - consider a flow for which ˝L « vT˝.


¶ *define* {{< ℑ flow speed >}} : the magnitude of the flow velocity vector.
  
¶ *define* {{< ℑ velocity profile >}} : the flow velocity evaluated along a 
  line.
