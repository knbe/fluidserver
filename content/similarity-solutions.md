---
title: "diffusion, similarity solutions, intermediate asymptotics"
type: long
---

# RECAP: ANOMALOUS DIMENSIONS
--------------------------------------------------------------------------------

¶ when anomalous dimensions arise, it means there's a microscopic length at 
  work. 
  - this microscopic length scale affects the thermo functions and the 
    correlation function _asymptotically_ near the critical point
  - mmly this means you can't approximate a function ˝f(x)˝ with ˝f(x = 0)˝ when 
    ˝x → 0˝. that kind of limit approximation is not valid.

¶ so basically, whenever there's a function ˝f(x)˝ that you _can't_ replace with 
  ˝f(0)˝ when ˝x˝ is small, it means there's an anomalous dimension. that's all 
  an anomalous dimension is, really.
  - when you look at ADs this way (as a general mml object/form/statement), 
    obviously, you can start applying them to other things too
  - >> did anomalous dimensions arise in physics, when studying phase 
    transitions? <<

¶ you can calculate ADs via RG methods for certain nonlinear diffusion problems 
  from fluid dynamics.
  - main difference between this and the study of phase transitions:
    - these are far from equilibrium (FFE) systems
    - they are formulated as PDEs rather than in terms of a partition function
  - but they still give rise to anomalous diffusion laws

¶ in "conventional" 1d diffusion, the mean square displacement of a particle 
  from the starting point, as a fn of time, is ˝⟨x⁽2⁾⟩ ∼ t˝. BUT the actual 
  problems give laws of form ˝⟨x⁽2⁾⟩ ∼ t⁽1-α⁾˝, where ˝α˝ is an AD.
  - in all these problems, the long term behaviour is governed by a __similarity 
    solution__, but you can't actually deduce the similarity variables from 
    dimensional analysis

¶ the general form of these problems (true for both FFE fluids and critical 
  phenomena):
  - you encounter a divergent perturbation series
  - you resolve this with renormalisation
  - renormalisation solves the divergences, but by itself doesn't give ADs
  - the renormalisation process introduces an arbitrary length scale ˝μ˝ that is 
    _not_ present in the original problem, and thus it also can't appear in the 
    solution
  - ie the solution has an _invariance_ wrt variations of ˝μ˝
  - this invariance is what renormalisation expresses.
  - you can exploit renormalisation, along with an approximation scheme (there 
    are many), to calculate the ADs

# THE DIFFUSION EQUATION
--------------------------------------------------------------------------------

¶ the 1d diffusion equation starting from a localised initial condition:
  ```
    𝝏{t}{u(x,t)} = ÷12·κ·𝝏n{2}{x}{u(x,t)}       for: -∞ < x < ∞
  ```
  - where ˝κ˝ is the diffusion coefficient
  - the initial condition is
  ```
    u(x,t=0) = ÷{A₍0₎}{√{2πl⁽2⁾}}·exp(-x⁽2⁾/2l⁽2⁾)
  ```
  - ˝l˝ is the width of the initial distribution
  - ˝A₍0₎˝ is the area under the initial distribution, aka the mass ˝m˝ of the 
    distribution
  ```
    m = ∫{-∞}{∞} ɗx u(x,t)
    = A₍0₎    for: t ≥ 0
  ```
  - ?? is ˝u(x,t)˝ the density of the material at position ˝x˝ and time ˝t˝

¶ we're assuming the area under the initial distribution is fixed.

¶ in 3d:
  ```
    𝝏{t}{u(↗r,t)} = ∇⦁(D(u,↗r)·∇u(↗r,t))
  ```
  - ˝D(u,↗r)˝ is the collective diffusion coefficient for density ˝u˝ at 
    position ˝↗r˝
  - if ˝D˝ is constant, you get the linear differential equation
  ```
    𝝏{t}{u(↗r,t)} = D·∇⁽2⁾u(↗r,t)
  ```
  - this form is the same as the heat equation

# LT BEHAVIOUR OF THE DIFFUSION EQUATION
--------------------------------------------------------------------------------

¶ for the solution to be physically relevant/plausible, the solution should 
  vanish "sufficiently" fast at spatial infinity so that ˝m˝ is well defined, 
  and it should also have continuous spatial derivatives up to 2nd order so
  ```
    u(x,t) → 0    as    |x| → ∞
  ```
  - all we're really saying here is the diffusion should be over some finite 
    range, we're not considering diffusion over the entirety of space. at a 
    certain point, when you go far enough away, you can assume the density is 
    just zero.

¶ the mass ˝m˝ is conserved. the diffusion eqation comes from a conservation 
  law. 

¶ after time ˝t˝ the solution is
  ```
    u(x,t) = ÷{A₍0₎}{√{2π(κt+l⁽2⁾)}}·exp(-x⁽2⁾ / 2(κt+l⁽2⁾)) \tag{1}
  ```
  - after a long time, when ˝t » l⁽2⁾/κ˝, this reduces to
  ```
    u(x,t) ∼ ÷{A₍0₎}{√{2πκt}}·exp(-x⁽2⁾/2κt)    as    t → ∞   \tag{2}
  ```
  - note, you can also get this by keeping ˝t˝ fixed but making ˝l˝ small, ie 
    ˝l⁽2⁾ « κt˝
  ```
    u(x,t) ∼ ÷{A₍0₎}{√{2πκt}}·exp(-x⁽2⁾/2κt)    as    l → ∞   \tag{3}
  ```
  - wtf? ok ok, look, we're just looking at the form of 𝓮𝓻{1}. to make it look 
    like 𝓮𝓻{2}, just take ˝l → 0˝. that's all.

¶ now look at the initial condition. in the limit ˝l → 0˝ the initial condition 
  becomes
  ```
    u(x,t=0) = A₍0₎·δ(x)
  ```
  - all this is saying is, if the initial width ˝l˝ is infinitesimally small, 
    then the density at time ˝t = 0˝ is just a delta function equal to the mass 
    of the distribution

¶ the long time behaviour of the initial value problem with ˝l ≠ 0˝ is given by 
  the degenerate limit of the initial value problem with ˝l → 0˝.
  - the solution in this limit is the __green function__ for the diffusion 
    equation.
  - ?? wtf? surely not though? taking ˝l → 0˝ surely doesn't actually reveal 
    anything about the behaviour though? we're just playing around with 
    mathematical forms
    - oh oh  oh oh ho. got it.
    - firsty, read about fucking [degenerate distributions][1]
    - basically, it's a deterministic distribution that takes only a single 
      value, and it only has support at a single point (although that's kinda 
      weird af tho)
    - basically, look at the initial condition. the long term form of this 
      distribution (long term means for large ˝t˝) is the same as the 
      - ok, no. fuck.
      - arrgh
    - ok. look at the initial condition. good. now look at the time dependent 
      form of the initial condition (fuck me, ie, the fucking solution, ie, 
      𝓮𝓻{1}). the long term form of 𝓮𝓻{1} (long term means large ˝t˝) is the 
      same as the small ˝l˝ form of 𝓮𝓻{1} (ie take ˝l˝ to zero)

[1]: https://en.wikipedia.org/wiki/Degenerate_distribution

¶ the solution in the limit ˝l → 0˝ is the __green function for the diffusion 
  equation__
  - read [wikipedia][2]
  - also read "green's function in physics", around p154

[2]: https://en.wikipedia.org/wiki/Degenerate_distribution

¶ the ˝l → 0˝ solution is a similarity solution, is it?

# DIMENSIONAL ANALYSIS OF THE DIFFUSION EQUATION
--------------------------------------------------------------------------------

¶ the main thing about the similarity solution (the ˝l → 0˝ limit, yes?) is 
  that it's dimensionally deficient.
  - ?? going to assume the similarity solution is 𝓮𝓻{3} 
  - the original problem is specified by variables ˝x,t,l,A₍0₎˝
  - the "degenerate problem" is specified by ˝x,t,A₍0₎˝

¶ the fact that ˝l˝ is no longer a parameter (in the degenerate problem) is very 
  powerful. this is what allows us to construct a similarity solution using 
  dimensional analysis.
  - hmph

¶ dimensions of quantities, in the system of units ˝ULT˝, where ˝U = [u]˝, and 
  ˝U˝ is independent of ˝LT˝
  ```
    [u] = U
    [x] = L
    [l] = L
    [t] = T
    [A₍0₎] = UL
    [κ] = L⁽2⁾T⁽-1⁾
  ```

¶ dimensionless groups:
  ```
    Π = ÷{u}{A₍0₎}·√{κt} 
    Π₍1₎ = ÷{x}{√{κt}}
    Π₍2₎ = ÷{l}{√{κt}}
  ```
  - all other dimless groups of parameter can be constructed from these

¶ since the ˝Π˝s are dimless, then
  ```
    Π = f(Π₍1₎, Π₍2₎)
  ```
  - ˝f˝ is an unknown function, tbd. ˝f˝ "represents" the solution to the 
    problem
  - ˝f˝ is a scaling function. it's the scaling function for the original 
    problem. 
    - related to the static scaling hypothesis.

¶ for the similarity solution, ˝l˝ doesn't appear in the parameters (for the 
  degenerate problem), so
  ```
    Π = f₍s₎(Π₍1₎)
  ```
  - ˝f₍s₎˝ is the scaling function for the similarity solution.

¶ to determine ˝f₍s₎˝:
  - let ˝ξ = x / √{κt}˝
  - from DA, the solution has to be of form
  ```
    u(x,t) = ÷{A₍0₎}{√{κt}}·f₍s₎(ξ)
  ```
  - the LHS dims are ˝U˝, the RHS dims are ˝U˝ times a dimless function

¶ now sub this assumed form into the diffusion equation. you get an ODE for the 
  unknown function ˝f₍s₎˝:
  ```
    f₍s₎'' + ξf₍s₎' + f₍s₎ = 0    \tag{4}
  ```
  - although, more specifically, 
  ```
    Ɗn{2}{ξ}{f₍s₎(ξ)} + ξ·Ɗ{ξ}{f₍s₎(ξ)} + f₍s₎(ξ) = 0
  ```
  - or
  ```
    ÷{d⁽2⁾ f₍s₎(ξ)}{dξ⁽2⁾} + ξ·÷{df₍s₎(ξ)}{dξ} + f₍s₎(ξ) = 0
  ```

  {{< fig ssoldiffusion.jpg 7 >}}

¶ the ODE must satisfy:
  1. since ˝u(x,t) → 0˝ as ˝|x| → ∞˝,
  ```
    f₍s₎(x) → 0   as    |x| → ∞
  ```
  2. from the conservation law, 
  ```
    ∫{-∞}{∞} ɗξ f₍s₎(ξ) = 1
  ```
  3. ˝f₍s₎˝ must be an even function of ˝ξ˝ (this is because of the form of 
  𝓮𝓻{4}, and the fact that the IC is an even function), so 
  ```
    f₍s₎'(ξ = 0) = 0
  ```

¶ solve the ODE:
  - note that 𝓮𝓻{4} is an exact differential equation. ∴ you can integrate it, 
    to give
  ```
    f₍s₎' + ξf₍s₎ = C   \tag{5}
  ```
  - ?? I bet if you actually put an integration sign in front of all the terms 
    in 𝓮𝓻{4} and do the integration by parts for the middle term, there'll be 
    some term that cancels with the third term, and presto, etc
  - the constant of integration ˝C˝ must be zero, because when ˝ξ = 0˝, ˝f₍s₎'˝ 
    must be zero (since ˝f₍s₎˝ is even)
  - integrate 𝓮𝓻{5}, you get
  ```
    f₍s₎(ξ) = B·exp{-ξ⁽2⁾/2}
  ```
  - the normalisation condition (ODE condition 2) gives ˝B˝
  ```
    B = 1 / √{2π}
  ```
  - ∴ the (similarity) scaling function (is that what it's called? wtf is 
    ˝f₍s₎˝?) is
  ```
    f₍s₎(ξ) = ÷{1}{√{2π}}·exp{-ξ⁽2⁾/2}
  ```
  - so the similarity solution is
  ```
    u(x,t) = ÷{A₍0₎}{√{κt}}·÷{1}{√{2π}}·exp{-x⁽2⁾/2κt}  
  ```

# INTERMEDIATE ASYMPTOTICS OF THE FIRST KIND
--------------------------------------------------------------------------------

¶ for the similarity solution, 
  ```
    Π = f₍s₎(Π₍1₎)
  ```
  - ˝f₍s₎˝ is the scaling function for the similarity solution.

¶ for any version of the problem where the IC is ˝l ≠ 0˝, the solution must be 
  of form
  ```
    Π = f(Π₍1₎, Π₍2₎)
  ```

¶ for long times, ˝Π₍2₎ → 0˝. ∴ according to common sense, at long times you can 
  assume ˝Π₍2₎˝ is small enough to be able to ignore (set to zero), ie
  ```
    f₍s₎(Π₍1₎) = f(Π₍1₎, [Π₍2₎ = 0])    \tag{6}
  ```
  
¶ basically, this common sense intuition is just the statement that a diffusion 
  process __loses memory of the initial distribution__ once ˝⟨x⁽2⁾⟩ » l⁽2⁾˝
  - turns out this assumption is NOT right for some problems
  - we verified this assumption when the IC is a gaussian. should try the 
    equivalent calcuation for an arbitrary IC. 

¶ the assumption that you can take the limit to get 𝓮𝓻{6} allows you to 
  determine the long time behaviour of the diffusion equation from the 
  similarity solution, starting from the IC with ˝l ≠ 0˝.

¶ __intermediate asymptotics__: the asymptotics of the long time limit
  - "intermediate", because the ultimate behaviour is ˝u = 0˝
  - the region where the 'common sense' assumption is correct is called 
    __intermediate asymptotics of the first kind__ (IA1)

¶ when you make the IA1K assumption, you can express the asymptotic behaviour of 
  the diffusion equation for long times by
  ```
    u(x,t) ∼ t⁽-1/2⁾·g(x / √{κt})
  ```
  - ˝g(x)˝ is a function that satisfies ˝g(x) → const˝ as ˝x → 0˝

¶ the most common, unconscious assumption, is that asymptotics are of the first 
  kind.
  - given a physical problem expressed in dimless variables ˝Π, Π₍1₎, Π₍2₎...˝, 
    the solution has the form
  ```
    Π = f(Π₍1₎, Π₍2₎,...)
  ```
  - where ˝f˝ is a function that can ONLY be determined from a detailed analysis 
    of the problem.
  - if the limiting behaviour as ˝Π₍2₎ → 0˝ has form
  ```
    Π ∼ f(Π₍1₎, 0, ...)
  ```
  - then asymptotics are of the first kind.

¶ the importance of similarity solutions:
  - they are easy to construct. 
  - they satisfy an equation with one fewer independent variable than the 
    original PDE
  - the intermediate asymptotics of solutions that are themselves NOT similarity 
    solutions are still often given by similarity solutions

# WHERE ANOMALOUS DIMENSIONS COME IN
--------------------------------------------------------------------------------

¶ you can't always get similarity solutions using dimensional analysis, because 
  ADs can occur.
