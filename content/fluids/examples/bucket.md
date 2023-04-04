---
time: 202302141713
title: "bucket"
type: example
---

how long does it take for a bucket with a small hole in the side to empty?

you can start with the continuity equation:
```
  A₍1₎ v₍1₎ = A₍2₎ v₍2₎
```

the flux out:
```
  A₍2₎ √{2gh}
```

convert to volumetric flux:
```
  V = A₍2₎v₍2₎t
```

so time taken is:
```
  t = V / A₍2₎√{2gh}
```

{{< fig bucket.png 10 >}}

[`attach table of results`]

not entirely sure this is correct. experimentally, I find it empties slower. 
perhaps this is because of viscosity? are we operating in some kind of 
approximation limit here? I mean, I know we are, but which one?
