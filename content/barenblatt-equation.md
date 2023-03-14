---
title: "barenblatt equation"
type: long
---

# BARENBLATT'S EQUATION

¶ recall, the modified porous medium equation
  ```
    𝝏{t}{u(r,t)} = D·Δ₍d₎·u(r,t)⁽1+n⁾
  ```

  the case ˝n = 0˝ is the barenblatt equation. this is a fluid that can expand 
  and contract irreversibly in response to a fluid flow through it.
  - ?? what does it mean, to expand and contract _irreversibly_?

# DIMENSIONAL ANALYSIS OF BARENBLATT'S EQUATION
--------------------------------------------------------------------------------

¶ barenblatt's equation in 1d:
  ```
    𝝏{t}{u(x,t)} = Dκ·𝝏n{2}{x}{u(x,t)}
  ```
  - where
  ```
    D
    == ÷12            𝝏{t}{u} > 0
    == ÷{1+ε}{2}      𝝏{t}{u} < 0
  ```
  
  ˝κ˝ and ˝ε˝ are constants. ˝κ˝ stands in for the combination of constants in 
    the elasto-plastic porous medium equation (˝κ,ρ,g,μ,σ˝). ˝ε˝ represents the 
    constant term you have to add to include the dynamical asymmetry.

  ˝[κ] = L⁽2⁾T⁽-1⁾˝. ˝ε˝ is a pure number (dimensionless).

¶ consider an initial condition of form
  ```
    u(x,t=0) = ÷{A₍0₎}{l}·φ(÷xl)
  ```
  - ˝l˝ is the initial width, ˝A₍0₎˝ is the area under the distribution.
  - ˝φ˝ is a function that represents the "profile" of the distribution. in the 
    case of 1d diffusion, recall we used a gaussian profile, so ˝φ = 
    exp{x⁽2⁾/2l⁽2⁾}˝.

  ˝u(x,t=0)˝ and ˝φ(x)˝ obey the normalisation:
  ```
    ∫{-∞}{∞} ɗx u(x,0) = A₍0₎
    ∫{-∞}{∞} ɗz φ(z) = 1
  ```

¶ dimensionless groups for the problem (same reasoning as for 1d diffusion 
  equation):
  ```
    Π = ÷{u}{A₍0₎}·√{κt}
    Π₍1₎ = ÷{x}{√{κt}}
    Π₍2₎ = ÷{l}{√{κt}}
    Π₍3₎ = ε
  ```

  all the other dimensionless groups of parameters can be constructed from 
  this set. since the ˝Π˝'s are dimensionless, the solution to the problem must 
  be of form
  ```
    Π = f(Π₍1₎, Π₍2₎, Π₍3₎)
  ```
  - where ˝f˝ is a scaling function that represents the solution to the problem

¶ now look at long term considerations. for long times ˝Π₍2₎ → 0˝. use the 
  reasoning from earlier, when you did dimanal for the diffusion equation. the 
  long term asymptotics can be represented either by the long ˝t˝ limit or the 
  ˝l → 0˝ limit. the latter is the similarity solution. 

  for the similarity solution, ˝l˝ doesn't appear in the parameters, so you 
  define a relation like ˝Π = f₍s₎(Π₍1₎, Π₍3₎)˝, where ˝f₍s₎˝ is the scaling 
  function for the similarity solution. 

  to find ˝f₍s₎˝, let ˝ξ = x / √{κt}˝, and from DA the solution should be of 
  form
  ```
    u(x,t) = ÷{A₍0₎}{√{κt}}·f(ξ,ε)
  ```
  - just using ˝f˝ instead of ˝f₍s₎˝

  ˝u˝ has to be even, and it has to vanish monotonically at ∞.

¶ let the +ve values of ˝x˝ where ˝𝝏{t}{u(x,t)} = 0˝ be ˝X(t,ε)˝, and let the 
  correspond value of ˝ξ˝ be ˝ξ₍0₎˝, 
  ```
    ξ₍0₎ = ÷{X(t,ε)}{√{κt}}
  ```
  - ?? is this analagous to the role of ˝r₍0₎˝ in the porous equation?

  ˝ξ₍0₎˝ is a dimensionless constnat.

¶ substitute this into the barenblatt equation, you get two ODEs for the scaling 
  function ˝f˝, one valid for ˝𝝏{t}{u} < 0˝ and the other for ˝𝝏{t}{u} > 0˝
  ```
    (1+ε)·f'' + (ξf)' = 0     for: 0 ≤ ξ ≤ ξ₍0₎
    f'' + (ξf)' = 0           for: ξ₍0₎ ≤ ξ ≤ ∞
  ```
  - ?? I guess I still don't really get what ˝ξ˝ actually is. it looks a helluva 
    lot like ˝r˝ in the porous medium problem. it's got the whole asymmetry 
    thing about a certain value of it, etc.

¶ integrate the ODEs, you get
  ```
    (1+ε)·f' + (ξf) = B₍1₎    for: 0 ≤ ξ ≤ ξ₍0₎ 
    f' + (ξf) = B₍2₎          for: ξ₍0₎ ≤ ξ ≤ ∞
  ```
  - the ˝B˝s are constants of integration.

  recall ˝f(ξ)˝ is required to be even. means that at ˝ξ = 0, f'(ξ) = 0˝ and 
  ∴ ˝B₍1₎ = 0˝.

  as ˝ξ → ∞˝ both ˝f˝ and ˝f'˝ must go to zero, so that ˝f˝ remains integrable 
  (ok...). ∴ ˝B₍2₎ = 0˝.

  integrate again, get
  ```
    f
    == C₍1₎·exp{-ξ⁽2⁾/2(1+ε)}     for: 0 ≤ ξ ≤ ξ₍0₎
    == C₍2₎·exp{-ξ⁽2⁾/2}          for: ξ₍0₎ ≤ ξ < ∞
  ```

¶ match ˝f˝ and ˝f'˝ at ˝ξ = ξ₍0₎˝:
  ```
    C₍1₎·exp{-ξ₍0₎⁽2⁾/2(1+ε)} = C₍2₎·exp{-ξ₍0₎⁽2⁾/2}
    ÷{C₍1₎}{1+ε}·exp{-ξ₍0₎⁽2⁾/2(1+ε)} = C₍2₎·exp{-ξ₍0₎⁽2⁾/2}
  ```

  the only solution to these equations is ˝C₍1₎ = C₍2₎ = 0˝ (trivial solution).

  conclusion: there is no nontrivial similarity solution of form ˝u(x,t) = 
  (A₍0₎/√{κt})·f(ξ,ε)˝ with continuous derivatives up to 2nd order.

¶ if you're an unlearned imbecile, you might assume this conclusion implies the 
  problem isn't well defined, that the derivatives develop singularities, when 
  considering the LT behaviour of the barenblatt equation with initial 
  conditions with ˝l ≠ 0˝.

  but, it turns out, because of course it does, that there is in fact a solution 
  to barenblatt's equation _with_ initial conditions ˝l ≠ 0˝, and that _does_ 
  have continuous derivatives up to second order, and a continuous derivative 
  wrt ˝t˝.

  it's just that the LT bhvr of the barenblatt equation is not of the form we 
  suspected, that is ˝u(x,t) = (A₍0₎/√{κt})·f(ξ,ε)˝.

  what you have to do, is construct a similarity solution WITH an anomalous 
  dimension!

# SIMILARITY SOLUTION WITH AN ANOMALOUS DIMENSION
--------------------------------------------------------------------------------

¶ ok, so, we know there's no similarity solution in the "conventional" sense (ie 
  conventional being the shiz we did for the diffusion equation). 

¶ recall, when you define the dimless groups, the form of the  should be
  ```
    Π = f(Π₍1₎, Π₍2₎, Π₍3₎)
    (e5)
  ```
  and we found just above that a solution of form ˝Π = f₍s₎(Π₍1₎, Π₍3₎)˝ doesn't 
  quite work out. 

  whither now?

¶ you can still find the asymptotic behaviour (pfft. can you know). what you do 
  is you _postulate_ that as ˝t → ∞˝ and ˝Π₍2₎ → 0˝, the equation (e5) becomes
  ```
    Π ∼ Π₍2₎⁽2α⁾·g(Π₍1₎, Π₍3₎)
    (e6)
  ```
  - ˝α˝ is an anomalous dimension tbd.
  - GF: this equation (e6) arises from RG. for now just follow along (aaaaa)

  equation (e6) suggests you should seek a solution to the barenblatt equation 
  with initial conditions of form
  ```
    u(x,t) = ÷{A₍0₎}{√{κt}}·÷{l⁽2α⁾}{(κt)⁽α⁾}·g(÷{x}{√{κt}}, ε)
  ```
