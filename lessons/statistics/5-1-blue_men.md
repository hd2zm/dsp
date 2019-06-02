[Think Stats Chapter 5 Exercise 1](http://greenteapress.com/thinkstats2/html/thinkstats2006.html#toc50) (blue men)

```python
import scipy.stats
mu = 178
sigma = 7.7
dist = scipy.stats.norm(loc=mu, scale=sigma)

low = dist.cdf(177.8)    # 5'10"
high = dist.cdf(185.4)   # 6'1"

print(low)
print(high)
print(high-low)
```

5'10": 0.48963902786483265

6'1": 0.8317337108107857

6'1" - 5'10": 0.3420946829459531)
