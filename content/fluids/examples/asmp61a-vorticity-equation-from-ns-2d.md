---
title: "deriving the vorticity equation from navier-stokes in 2d"
type: example
source: asmp61
---

Start with the incompressible Navier-Stokes equation
```
  𝝏₍t₎↗v + (↗v⦁∇)↗v = ν∇⁽2⁾↗v - ÷1ρ·∇p                             𝓮𝓺{611} 
```
where
- ˝↗v = ↗v(↗r,t)˝ is the flow velocity (vector field)
- ˝p = p(↗r,t)˝ is the pressure (scalar field)
- ˝ρ˝ is the density
- ˝ν˝ is the kinematic viscosity, ˝ν = μ/ρ˝

Some context: the NSE is an equation for the time evolution of the fluid's 
velocity field. The specific form of the equation derives from momentum 
conservation (and whatever assumptions you deign to make about the fluid, e.g.
incompressibility). The LHS of \eqref{611} is an expression for the rate of 
change of flow velocity, ˝Ɗ₍t₎↗v˝, where ˝Ɗ₍t₎˝ is the [advective 
derivative][1a] ˝Ɗ₍t₎ = 𝝏₍t₎ + ↗v⦁∇˝.  The RHS is the total force density (force 
per unit mass) from all the forces on the fluid. Here we're only considering 
internal contributions from viscosity and pressure. If there were external 
forces, they'd appear as additional terms on the RHS.

[1a]: https://wikiless.org/wiki/Substantive_derivative?lang=en

Vorticity is defined as the curl of the flow velocity, ˝↗ω = ∇×↗v˝. You can 
derive an equation for the time evolution of vorticity by taking the curl of the 
NSE \eqref{611}:
```
  ∇×(𝝏₍t₎↗v) + ∇×((↗v⦁∇)↗v) = ∇×(ν∇⁽2⁾↗v) - ∇×(÷1ρ·∇p)          𝓮𝓺{612}
```
Let's go through these terms one by one. I'm going to use Levi-Civita notation 
to keep things concise (see Appendix 6-1A for some rather more hideous brute 
force vector math). In Levi-Civita notation, the cross product ˝↗v×↗w˝ is 
expressed ˝ε₍ijk₎v₍j₎w₍k₎˝.  Thus, the first term on the LHS of \eqref{612} is
```
  ∇×(𝝏₍t₎↗v)
  == 𝝏₍i₎(𝝏₍t₎v₍j₎)ε₍ijk₎
  == 𝝏₍t₎(𝝏₍i₎v₍j₎ε₍ijk₎)
  == 𝝏₍t₎(∇×↗v)
```
```
  == 𝝏₍t₎↗ω                                 𝓮𝓺{614}
```
where in step 2 I've used the [symmetry of second derivatives][1] to swap the 
˝𝝏₍i₎˝ and ˝𝝏₍t₎˝ derivatives.

[1]: https://en.wikipedia.org/wiki/Symmetry_of_second_derivatives

Now for the second term on the LHS of \eqref{612}. There is more than one way to 
go about this --- in Appendix 6-1A you can see a full brute force expansion of 
the vector terms.  Here though, I shan't be so uncouth. First, note the vector 
identity
```
  (↗v⦁∇)↗v = ÷12∇(↗v⦁↗v) - ↗v×(∇×↗v)
```
To prove this identity, take ith component of each term (in LC notation),
{{< M >}}
  v₍j₎𝝏₍j₎v₍i₎ == ÷12𝝏₍i₎(v₍j₎⁽2⁾) - ε₍ijk₎v₍j₎ \underbrace{ (∇×↗v)₍k₎ 
  }_{=ε₍klm₎𝝏₍l₎v₍m₎} == ÷12𝝏₍i₎(v₍j₎⁽2⁾) - ε₍ijk₎ε₍klm₎v₍j₎𝝏₍l₎v₍m₎
  == \underbrace{ ÷12𝝏₍i₎(v₍j₎⁽2⁾) }_{ =v₍j₎𝝏₍i₎v₍j₎ }
  - \underbrace{ (δ₍il₎δ₍jm₎ - δ₍im₎δ₍jl₎)v₍j₎𝝏₍l₎v₍m₎ }_{=v₍j₎𝝏₍i₎v₍j₎ - 
    v₍j₎𝝏₍j₎v₍i₎}
  == v₍j₎𝝏₍i₎v₍j₎ - v₍j₎𝝏₍i₎v₍j₎ + v₍j₎𝝏₍j₎v₍i₎
  == v₍j₎𝝏₍j₎v₍i₎
{{< /M >}}

∴ LHS = RHS. Now take the curl,
```
  ∇×(÷12∇(↗v⦁↗v) - ↗v×∇×↗v)
  == ε₍ijk₎𝝏₍j₎(÷12∇(↗v⦁↗v))₍k₎ - ε₍ijk₎𝝏₍j₎(↗v×∇×↗v)₍k₎
  == ÷12 ε₍ijk₎𝝏₍j₎𝝏₍k₎v₍l₎⁽2⁾ - ε₍ijk₎𝝏₍j₎(v₍l₎𝝏₍k₎v₍l₎ - v₍l₎𝝏₍l₎v₍k₎)
  == ÷12 ε₍ijk₎𝝏₍j₎𝝏₍k₎v₍l₎v₍l₎ - ε₍ijk₎𝝏₍j₎v₍l₎𝝏₍k₎v₍l₎ + ε₍ijk₎𝝏₍j₎v₍l₎𝝏₍l₎v₍k₎
  == \underbrace{ ε₍ijk₎𝝏₍j₎v₍l₎𝝏₍k₎v₍l₎ - ε₍ijk₎𝝏₍j₎v₍l₎𝝏₍k₎v₍l₎ }_{=0} + ε₍ijk₎𝝏₍j₎v₍l₎𝝏₍l₎v₍k₎
  == ε₍ijk₎𝝏₍j₎v₍l₎𝝏₍l₎v₍k₎
  == (v₍l₎𝝏₍l₎)(ε₍ijk₎𝝏₍l₎v₍k₎)
  == (↗v⦁∇)(∇×↗v)
  == (↗v⦁∇)↗ω
```
∴
```
  ∇×(↗v⦁∇)↗v = (↗v⦁∇)↗ω               𝓮𝓺{615}
```

Next, the viscosity term (first term on the RHS of \eqref{612}):
```
  ∇×(ν·∇⁽2⁾↗v)
  == 𝝏₍i₎·(ν·∇⁽2⁾↗v)₍j₎·ε₍ijk₎
  == 𝝏₍i₎·(ν·𝝏₍l₎⁽2⁾v₍j₎)·ε₍ijk₎
  == ν·𝝏₍l₎⁽2⁾(𝝏₍i₎↗v₍j₎ε₍ijk₎)
  == ν·∇⁽2⁾(∇×↗v)
```
```
  == ν·∇⁽2⁾↗ω                             𝓮𝓺{616}
```

Finally, the pressure term (second term on the RHS of \eqref{612}). Since we're 
taking the curl of the gradient of pressure, ˝∇×(÷1ρ·∇p)˝, which is a scalar 
field, this term is zero.

When you combine the results from \eqref{614}, \eqref{615}, \eqref{616}, you get
```
  𝝏₍t₎↗ω + (↗v⦁∇)↗ω = ν∇⁽2⁾↗v           𝓮𝓺{616a}
```
So far I've kept all the vector expansions general, for a 3D vorticity vector 
˝↗ω˝. For 2D flows where ˝↗v˝ is defined in the ˝xy˝ plane, you can use the 
scalar vorticity, ˝ω = ↑z⦁(∇×↗v)˝ and, taking the ˝↑z˝ component of \eqref{616a} 
gives
```
  𝝏₍t₎ω + (↗v⦁∇)ω = ν∇⁽2⁾↗v
```

Next, note that the incompressibility condition, ˝∇⦁↗v = 0˝, implies the 
velocity field is solenoidal (zero divergence) and can be expressed as the curl 
of a vector potential,
```
  ↗v = ∇×↗ψ           𝓮𝓺{617}
```
where ˝↗ψ˝ is the stream function. For 2D flows, where ˝↗v˝ has components only 
in the ˝xy˝ plane, then ˝↗ψ = (0,0,ψ)˝, and you can write the stream function 
as a scalar function, ˝ψ˝. 

In term of the scalar ˝ψ˝, the curl in \eqref{617} can be expressed ˝↗v = 
-∇×(ψ↑z)˝. The negative sign is a matter of convention (supposedly [common in 
meterology and oceanography][4]). Explicitly computing this cross product gives 
an expression for the components of ˝↗v˝ in terms of ˝ψ˝:
{{< M >}}
  ↗v = -∇×(ψ↑z) = -\begin{vmatrix}
    ↑x & ↑y & ↑z \\
    𝝏₍x₎ & 𝝏₍y₎ & 𝝏₍z₎ \\
    0 & 0 & ψ
  \end{vmatrix}
  = (-𝝏₍y₎ψ)↑x + (𝝏₍x₎ψ)↑y
{{< /M >}}
The definition of vorticity means you can also write ˝ω = ∇⁽2⁾ψ˝. Combining 
these results, you can rewrite the advection term in \eqref{616a} as
```
  (↗v⦁∇)↗ω
  == (-𝝏₍y₎ψ𝝏₍x₎ + 𝝏₍x₎ψ𝝏₍y₎)ω
  == 𝝏₍x₎ψ 𝝏₍y₎ω - 𝝏₍x₎ω 𝝏₍y₎ψ
  == J(ψ,ω)
```
where ˝J˝ is the Jacobian. The vorticity equation becomes
```
  𝝏₍t₎ω + J(ψ,ω) = ν⁽2⁾ω
```

[4]: https://en.wikipedia.org/wiki/Stream_function#Alternative_definition_(opposite_sign)


{{< fig L1010778.jpg 13 >}}

        Appendix 6-1A. The blackboard.
