---
title: "the vorticity equation in a rotating frame"
type: example
source: asmp62
---

The NSE:
```
  Ɗ₍t₎↗v = ν∇⁽2⁾↗v - ÷1ρ∇p        𝓮𝓺{621}
```
where ˝Ɗ₍t₎˝ is the advective derivative, ˝Ɗ₍t₎ = 𝝏₍t₎ + (↗v⦁∇)˝. Suppose we're 
now in a rotating reference frame RF that's rotating at angular velocity ˝↗Ω˝ 
w.r.t. the inertial frame IF. Since all the vector quantities are now fixed in 
the rotating frame, you have to transform them to a form that's valid in the 
inertial frame. Let ˝↗r˝ be the position vector, ˝↗r = ∑₍i₎r₍i₎↑e₍i₎˝. The basis 
˝↑e₍i₎˝ is fixed in RF but rotating with angular velocity ˝↗Ω˝ in IF. Thus the 
time derivative of ˝↗r˝, as seen from IF, is
```
  (Ɗ₍t₎↗r)₍IF₎
  = Ɗ₍t₎(∑₍i₎r₍i₎↑e₍i₎)
  = ∑₍i₎(Ɗ₍t₎r₍i₎)↑e₍i₎ + ∑₍i₎r₍i₎ \underbrace{(Ɗ₍t₎↑e₍i₎)}_{=↗Ω×↑e₍i₎}
  = (Ɗ₍t₎↗r + ↗Ω×↗r)₍RF₎
```
where in the last line ˝↗r˝ is measured from the RF. Since ˝↗v = Ɗ₍t₎↗r˝, the 
transformation for velocity in rotating coordinates is
```
  (↗v)₍IF₎ → (↗v + ↗Ω×↗r)₍RF₎
```
(a) You also have to include fictitious forces to the RHS of \eqref{621}. Normally 
these are the Coriolis force ˝-2m↗Ω×↗v˝ and the centrifugal force 
˝-m↗Ω×(↗Ω×↗r)˝. In this problem we consider only the Coriolis force. The NSE in 
rotating coordinates becomes
```
  (Ɗ₍t₎↗v)₍IF₎ = (ν∇⁽2⁾(↗v+↗Ω×↗r) - ÷1ρ∇p - 2↗Ω×↗v)₍RF₎
```
However, it turns out when you expand out the viscosity term, the contribution 
from the ˝↗Ω×↗r˝ term cancels out:
```
  ∇⁽2⁾(↗Ω×↗r)
  = 𝝏₍l₎⁽2⁾(Ω₍j₎r₍k₎ - Ω₍k₎r₍j₎)
  = (𝝏₍l₎⁽2⁾Ω₍j₎)r₍k₎ + Ω₍j₎(𝝏₍l₎⁽2⁾r₍k₎) - (𝝏₍l₎⁽2⁾Ω₍k₎)r₍j₎ - Ω₍k₎(𝝏₍l₎⁽2⁾r₍j₎)
  = 0
```
so the viscosity term actually stays the same, ˝ν∇⁽2⁾↗v˝, and the equation is
```
  (Ɗ₍t₎↗v)₍IF₎ = (ν∇⁽2⁾↗v - ÷1ρ∇p - 2↗Ω×↗v)₍RF₎
```
(b) Now, take the curl ˝↑z⦁∇×˝ of both sides:
{{< M >}}
  ↑z⦁(∇×Ɗ₍t₎↗v) = ↑z⦁(∇×ν∇⁽2⁾↗v) - ↑z⦁(∇×÷1ρp) - ↑z⦁(∇×(2↗Ω×↗v))
{{< /M >}}
As demonstrated in the previous problem, the LHS is ˝𝝏₍t₎ω + J(ψ,ω)˝, the 
viscosity term is ˝ν∇⁽2⁾ω˝, and the pressure term is zero. For the Coriolis 
term, substitute ˝2↗Ω = ↑zf(y)˝, where ˝f(y) = f₍0₎ + βy˝, and you get

{{< M >}}
  2↗Ω×↗v == ↑zf×↗v == \begin{vmatrix}
    ↑x & ↑y & ↑z \\
    0 & 0 & f \\
    v₍x₎ & v₍y₎ & 0
  \end{vmatrix}
  == (-fv₍y₎)↑x + (fv₍x₎)↑y
{{< /M >}}
and, taking the curl ˝↑z⦁∇×˝ gives
```
  ↑z⦁∇×(↑zf×↗v)
```
{{< M >}}
  == ↑z⦁
  \begin{vmatrix}
    ↑x & ↑y & ↑z \\
    𝝏₍x₎ & 𝝏₍y₎ & 𝝏₍z₎ \\
    -fv₍y₎ & fv₍x₎ & 0
  \end{vmatrix}
  == 𝝏₍x₎fv₍x₎ + 𝝏₍y₎fv₍y₎
{{< /M >}}
Putting this all together,
```
  𝝏₍t₎ω + J(ψ,ω) = ν∇⁽2⁾↗v - (𝝏₍x₎fv₍x₎ + 𝝏₍y₎fv₍y₎)
```
From the previous problem we know that ˝v₍x₎ = -𝝏₍y₎ψ˝ and ˝v₍y₎ = 𝝏₍x₎ψ˝.  
Substituting these in, the ˝f˝ term on the RHS becomes ˝-𝝏₍x₎f𝝏₍y₎ψ + 
𝝏₍y₎f𝝏₍x₎ψ˝. You can then combine this term with the Jacobian on the LHS
```
  𝝏₍t₎ω + (𝝏₍x₎ψ(𝝏₍y₎ω + 𝝏₍y₎f)- (𝝏₍x₎ω + 𝝏₍x₎f)𝝏₍y₎ψ) = ν∇⁽2⁾↗v
```
∴
```
  𝝏₍t₎ω + J(ψ,ω+f) = ν∇⁽2⁾↗v
```
And, I only just realised, the problem says we may ignore viscosity by setting 
˝ν = 0˝. In that case,
```
  𝝏₍t₎ω + J(ψ,ω+f) = 0
```

(c) Now we assume vorticity is small, ˝|ω| « |f(y)|˝, where ˝f(y) = f₍0₎ + βy˝ 
gives how the local vertical component of the planet's angular velocity depends 
on the latitude ˝y˝ (the planetary vorticity as a function of latitude). The 
˝|ω| « |f|˝ approximation means we're now thinking of the flow components ˝v₍x₎, 
v₍y₎˝ as perturbations. If you let ˝V˝ be the total flow field, then
```
  V₍x₎ = V₍m₎ + v₍x₎(t)
  V₍y₎ = v₍y₎(t)
```
where ˝V₍m₎˝ is the "zonal mean flow", aka the "average westerly", which acts in 
the ˝x˝ direction and is something that you assume to be constant. The 
approximation ˝|ω| « |f(y)|˝ means the perturbation flow doesn't advect the 
vorticity, so you can linearise the equation
```
  d₍t₎(ω + f) = 𝝏₍t₎ω + V₍m₎𝝏₍x₎ω +  β v₍x₎
```
where ˝β = 𝝏₍y₎f˝.

Substituting in ˝ω = ∇⁽2⁾ψ˝, 
```
  𝝏₍t₎∇⁽2⁾ψ + V𝝏₍x₎∇⁽2⁾ψ + β𝝏₍x₎ψ       𝓮𝓺{6214}
```

(d)  Look for plane wave solutions ˝ψ(x,y,t) = A·exp(i(↗k⦁↗x - σt))˝, where 
˝↗k⦁↗x = kx + ly˝. Plugging this into \eqref{6214}, you get
```
  ω(x,y,t) = -(k⁽2⁾+l⁽2⁾) ψ(x,y,t)
```
This gives the dispersion relation
```
  σ(k,l) = Vk - βk / (k⁽2⁾+l⁽2⁾)
```
These Rossby waves have phase speed
```
  ÷ωk = V₍m₎ - β / (k⁽2⁾ + l⁽2⁾)
```
As ˝β → 0˝, the phase speed ˝÷ωk → V₍m₎˝ (the zonal mean flow, the average flow 
before perturbations due to the Coriolis force are introduced). Since ˝β = 𝝏₍y₎f = 
𝝏₍y₎(2↗Ω)˝, ˝β˝ is proportional to the rate of change of Coriolis acceleration 
in the vertical "meridional" direction. Hence as you approach the poles, ˝β → 
0˝, and at the poles there are no Rossby waves.

REFERENCES

K. Thorne, R. Blandford, Modern Classical Physics. Chapter 14.2 _Vorticity_, 
chapter 14.5 _Nearly Rigidly Rotating Flows_, chapter 16.4 _Rossby Waves in a 
Rotating Fluid_.

Wikipedia, _Rossby wave, Mathematical definitions_. https://en.wikipedia.org/wiki/Rossby_wave#Mathematical_definitions
