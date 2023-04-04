---
time: 202304041727
title: "power spectrum of a cube"
type: example
source: 
---

A cosmological cube:

{{< fig cube.png 12 >}}

The contrast in the image shows (somewhat) the local variations in the 
(over)density field. The power spectrum is essentially a measure of the _density 
contrast_ in space.

Some theory: the _fractional overdensity_ ˝δ(⬀x)˝ describes the deviation of the 
density field, ˝ρ(⬀x)˝, from the average density, ˝⟨ρ⟩˝
```
  δ(⬀x) = ÷{ ρ(⬀x) - ⟨ρ⟩ }{ ⟨ρ⟩ }
```
where ˝ρ(⬀x)˝ is the density at point ˝⬀x˝ and ˝⟨ρ⟩˝ is the average density over 
(all) space. So ˝δ(⬀x)˝ is a dimensionless scalar field.

The _two-point correlation function_ ˝ξ˝ can be defined in terms of the 
fractional overdensity as
```
  ξ(⬀x₍1₎, ⬀x₍2₎) = ⟨δ(⬀x₍1₎)δ(⬀x₍2₎)⟩ = ÷1V ∫ d⁽3⁾⬀xͺδ(⬀x₍1₎) δ(⬀x₍1₎-⬀x₍2₎)
```

And the _power spectrum_ ˝P(k)˝ can be defined in terms of ˝ξ˝ via the relation 
```
  ξ(⬀x₍1₎,⬀x₍2₎) = ∫ d⁽3⁾kͺ÷1{(2π)⁽3⁾} P(k) e⁽i⬀k⦁(⬀x₍1₎-⬀x₍2₎)⁾
```

So the power spectrum is basically the fourier transform of the correlation 
function. If you let ˝δ(⬀k)˝ be the fourier transform of the fractional 
overdensity ˝δ(⬀x)˝, then
```
  ⟨δ(⬀k₍1₎)δ⁽❄⁾(⬀k₍2₎)⟩ = (2π)⁽3⁾ͺδ⁽3⁾(⬀k₍1₎-⬀k₍2₎) P(k)
```

˝P(k)˝ has dimensions of length˝⁽3⁾˝, so you can also define the _dimensionless 
power spectrum,_
```
  Δ⁽2⁾(k) = ÷{k⁽3⁾}{2π⁽2⁾} P(k)
```

To compute ˝P(k)˝, take the fourier transform of the overdensity field, then 
compute the correlation function and normalise

{{< fig spherical.png 10 >}}
{{< fig dimless.png 10 >}}

