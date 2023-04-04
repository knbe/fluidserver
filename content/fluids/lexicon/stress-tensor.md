---
time: 202304041714
title: "stress tensor"
type: lexicon
---

GOAL: describe the internal forces in a material/body in terms of a tensor.

# STRESSES & INTERNAL FORCES
--------------------------------------------------------------------------------

¶ the STRESSES in a material are the various internal forces that maintain its 
  form.

  suppose you dissect a 3d object with a plane. take a small area element of the 
  plane. the material on the left of the area element will exert a force ΔF to 
  the right, and v.v.

¶ PRESSURE in a static liquid is one kind of stress. in this case, F = P × A. 
  the force is perpendicular to the surface element.

¶ the force doesn't need to be normal to the surface. a SHEAR force is the 
  tangential component of a force across a surface. in solids and viscous 
  liquids in motion there are shear forces in addition to pressures.

# CONSTRUCTING THE STRESS TENSOR
--------------------------------------------------------------------------------

¶ feynman 31-6. make a cut perpendicular to the x axis. resolve the force across 
  the cut ΔF into three components, ΔF₍x₎, ΔF₍y₎, ΔF₍z₎. take the ratio of each 
  of these force components to the area element ΔyΔz. call these ratios S₍xx₎, 
  S₍xy₎, S₍xz₎.

  e.g. S₍yx₎ = ΔF₍y₎ / ΔyΔz

  then do the same for the y axis and the z axis. you end up with a 9-component 
  stress tensor.

# TENETS
--------------------------------------------------------------------------------

¶ the stress tensor is symmetric. it can be described by an ellipsoid with three 
  principal axes.

  stresses are simple for surfaces normal to these axes -- just pushes or pulls 
  perpendicular to surfaces. no shear forces. 

¶ for any stress, you can choose the axes so that the shear components are zero.

¶ if the ellipsoid is a sphere, there are ONLY normal forces in ANY direction. 
  corresponds to a hydrostatic pressure (the tensor is diagonal, all three 
  components are equal).

¶ the stress tensor will vary from point to point in a material. to describe the 
  whole block you need to give each component of S₍ij₎ as a function of 
  position. ∴ the stress tensor is a field. specifically, a tensor field. it 
  gives nine numbers for each point in space (six for the symmetric tensor). 

  ∴ to describe completely the internal forces in an arbitrarily distorted solid 
  requires six functions of x, y, z.
