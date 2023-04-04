---
time: 202304041725
title: "barotropic model of dark energy"
type: example
source: 
---

*Barotropic fluid:* a fluid where density is a function of pressure only 
(although a "perfect fluid" has a suspiciously similar definition...) The key 
thing is, the relation between pressure and density is given by ˝w = P/ρ˝, where 
˝w˝ is an equation of state parameter.

Define
```
  w' = ÷{dw}{dͺln(a)}
```

Insert ˝w = P₍X₎/ρ₍X₎˝ and use the product rule:
```mm
  w' &= ÷{d}{dͺln(a)} (P₍X₎⋄÷1{ρ₍X₎})
  &= ÷{dͺP₍X₎}{dͺln(a)} ÷1{ρ₍X₎} + P₍X₎ ÷{dͺρ₍X₎⁽-1⁾}{dͺln(a)}
  &= ÷{dͺP₍X₎}{dͺρ₍X₎} ÷{dͺρ₍X₎}{dͺln(a)} ÷1{ρ₍X₎} 
      - w ρ₍X₎ ÷1{ρ₍X₎⁽2⁾} ÷{dͺρ₍X₎}{dͺln(a)}
```
(in the last step: use the chain rule to expand ˝d₍ln(a)₎P₍X₎˝, and likewise for 
˝d₍ln(a)₎ρ₍X₎⁽-1⁾˝, and substitute ˝P₍X₎ = wρ₍X₎˝)

This simplifies to
```
  w' = ÷{dͺρ₍X₎}{dͺln(a)} ÷1{ρ₍X₎} ( ÷{dͺP₍X₎}{dͺρ₍X₎} - w) 
```

Using the scaling relationship of ˝ρ˝ with ˝a˝ from the previous problem, you 
can simplify the prefactor in the above expression to ˝-3(1+w₍X₎)˝. Then, 
substituting ˝dP₍X₎/dρ₍X₎ = c₍s₎⁽2⁾˝, you get
```
  w' = -3(1+w) (c₍s₎⁽2⁾ - w)
```

If ˝c₍s₎⁽2⁾ ≥ 0˝, then, by substituting ˝0 → c₍s₎⁽2⁾˝ into the equation, you can 
see that ˝w'˝ must satisfy ˝w' ≤ 3w(1+w)˝. Likewise if ˝c₍s₎⁽2⁾ ≤ 1˝ then ˝w' ≥ 
-3(1+w)(1-w)˝. And so you get
```
  -3(1+w)(1-w) ≤ w' ≤ 3w(1+w)
```
Since we're talking about dark energy, the e.o.s parameter ˝w˝ is necessarily ˝< 
0˝. Looking at the RH equality in ˝(6)˝, you can see that this implies ˝w' < 0˝ 
for barotropic dark energy fluids (however this observation is only valid if ˝w˝ 
is also ˝> -1˝, i.e. you're excluding scenarios that might lead to the "big 
rip").

(b) When you take the sound speed at the limit ˝c₍s₎ → c₍∞₎ = c₍s₎(a→∞)˝ then 
you end up with the equation
```
  ÷{dͺln(1+w)}{dͺln(a)} ≈ -3(1 + c₍∞₎⁽2⁾)
```
or
```
  (1+w) ≈ a⁽-3(1 + c₍∞₎)⁾
```

> (although, what are we really talking about here? When ˝a → ∞˝ aren't we 
  talking about the end of the universe?), 
{.question}

When you take this relation in the limit ˝c₍s₎ → c₍∞₎˝, you get ˝w → -1˝. And 
from this, you can derive the density relation
```
  ρ₍X₎ - ρ₍∞₎ ≈ a⁽-3(1+c₍∞₎⁽2⁾)⁾
```

So essentially, ˝ρ₍∞₎˝ is a constant that the density tends to approach as ˝a → 
∞˝, i.e. at very late times. This suggests you can write
```
  ρ₍X₎ = ρ₍∞₎ + ρ₍γ₎
```
or, in other words, the density of a barotropic fluid can be expressed as the 
sumn of a cosmological constant term and a positive e.o.s. fluid. Substituting 
an arbitrary ˝ρ₍γ₎ ≈ a⁽-3(1+w₍γ₎)⁾˝, you get ˝0 ≤ w₍γ₎ ≤ 1˝.
