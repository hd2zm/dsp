[Think Stats Chapter 4 Exercise 2](http://greenteapress.com/thinkstats2/html/thinkstats2005.html#toc41) (a random distribution)

```python
import thinkstats2
import thinkplot
import numpy as np

rand = np.random.random(1000)

pmf = thinkstats2.Pmf(rand)
thinkplot.Pmf(pmf, linewidth=0.1)

cdf = thinkstats2.Cdf(rand)
thinkplot.Cdf(cdf)
```

If the distribution is uniform, we should expect to se a linear, straight line for the CDF. We should also expect to see equal values in the PMF. Since that is almost the case, we can assume the distribution to be uniform. 
