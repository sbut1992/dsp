[Think Stats Chapter 5 Exercise 1](http://greenteapress.com/thinkstats2/html/thinkstats2006.html#toc50) (blue men)
import first
import nsfg
import numpy as np
import thinkstats2
import thinkplot
import scipy.stats

m = 178
sig = 7.7

x = scipy.stats.norm(m,sig)

five_ten = x.cdf(177.8)
six_one = x.cdf(185.4)
six_one-five_ten
