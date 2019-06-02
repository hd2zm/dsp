[Think Stats Chapter 2 Exercise 4](http://greenteapress.com/thinkstats2/html/thinkstats2003.html#toc24) (Cohen's d)

```python
import nsfg

#Take Cohen Effect Size from the book
def CohenEffectSize(group1, group2):
    """Computes Cohen's effect size for two groups.
    
    group1: Series or DataFrame
    group2: Series or DataFrame
    
    returns: float if the arguments are Series;
             Series if the arguments are DataFrames
    """
    diff = group1.mean() - group2.mean()

    var1 = group1.var()
    var2 = group2.var()
    n1, n2 = len(group1), len(group2)

    pooled_var = (n1 * var1 + n2 * var2) / (n1 + n2)
    d = diff / np.sqrt(pooled_var)
    return d

# Load data from pregnancy file and select live births
preg = nsfg.ReadFemPreg()
live = preg[preg.outcome == 1]

# Select first pregnancies and other pregnancies from live births
firsts = live[live.birthord == 1]
others = live[live.birthord != 1]

print(CohenEffectSize(firsts.totalwgt_lb, others.totalwgt_lb))
```

Cohen Effect Size: -0.088672927072602006. It seems that first babies are lighter than others. 

Pregnancy Length was positive (0.028879044654449883). So first babies have a longer pregnancy length than others. 

Both pregnancy length and total weight are similar in that they are very small. It is unlikely that anyone would notice this difference at all.
