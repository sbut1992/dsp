[Think Stats Chapter 3 Exercise 1](http://greenteapress.com/thinkstats2/html/thinkstats2004.html#toc31) (actual vs. biased)

import first
import nsfg
import numpy as np
import thinkstats2
import thinkplot

preg = nsfg.ReadFemPreg()
live = preg[preg.outcome == 1]

firsts = live[live.birthord == 1]
others = live[live.birthord != 1]

resp = nsfg.ReadFemResp()
pmf = thinkstats2.Pmf(resp['numkdhh'])


biased_pmf = pmf.Copy()

for x,y in pmf.Items():
    biased_pmf.Mult(x,x)
    
biased_pmf.Normalize()
biased_pmf

thinkplot.PrePlot(2)
thinkplot.Pmfs([pmf, biased_pmf])
thinkplot.Show(xlabel='children',ylabel='probability')


biased_pmf.Mean()
pmf.Mean()
