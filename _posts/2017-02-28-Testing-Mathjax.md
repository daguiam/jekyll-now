---
layout: post
title: Mathjax
categories: test math
tags: math
---

Testing mathjax


$$\sum_{n=1}^\infty 1/n^2 = \frac{\pi^2}{6}$$

$$ N_X^2\left(f,r\right) = 1 - \frac{f_{pe}^2\left(r\right)\left(1-\frac{f_{pe}^2\left(r\right)}{f^2}\right)}{f^2-f_{pe}^2\left(r\right)-f_{ce}^2\left(r\right)} $$


Ok that works


# Installation

Add a mathjax.html under ```_includes``` with

```
<script type="text/javascript" src="http://cdn.mathjax.org/mathjax/latest/MathJax.js?config=TeX-AMS-MML_HTMLorMML">
</script>
```

The code in markdown


```
$$\sum_{n=1}^\infty 1/n^2 = \frac{\pi^2}{6}$$
$$ N_X^2\left(f,r\right) = 1 - \frac{f_{pe}^2\left(r\right)\left(1-\frac{f_{pe}^2\left(r\right)}{f^2}\right)}{f^2-f_{pe}^2\left(r\right)-f_{ce}^2\left(r\right)} $$
```


```
def function(a,b):
  return a+b
```
