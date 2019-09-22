[Think Stats Chapter 2 Exercise 4](http://greenteapress.com/thinkstats2/html/thinkstats2003.html#toc24) (Cohen's d)

import first
import nsfg
import numpy as np

preg = nsfg.ReadFemPreg()
live = preg[preg.outcome == 1]

firsts = live[live.birthord == 1]
others = live[live.birthord != 1]

def custom_cohen(a,b):

    diff = a.mean()-b.mean()

    a_var = a.var()
    b_var = b.var()
    a_len,b_len = len(a),len(b)

    pooled_var = (a_len * a_var + b_len * b_var) / (a_len+b_len)
    d = diff / np.sqrt(pooled_var)
    return d

x = firsts.totalwgt_lb
y = others.totalwgt_lb

custom_cohen(x,y)

-0.088672927072602

This is a larger effect compared to the difference in pregnancy length for first babies and others of 0.028879044654449883

