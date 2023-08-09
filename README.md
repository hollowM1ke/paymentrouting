Modifications SplitAndAdjustSize:

added double alpha; line 19
modified public SplitAndAdjustSize(DistanceFunction df, double alpha) line 21
added this.alpha = alpha; line 24

getNextsVals method:
added double dynamicThreshold = alpha * totalSum + (1 - alpha) * maxCap; line 66
changed if(curVal <= dynamicThreshold) line 67

I also deleted blocks of code that were commented.
------------------------------------------------------------------------------------
Modifications PaymentTests:

runSimpleTestSynthetic:
modified new Transactions(400, -1, TransDist.EXP, false, 300000, true, false) line 56

modified Metric[] m array:

by changing 0.7 to other values of alpha I have tested my modified method.
new RoutePayment(new SplitAndAdjustSize(speedyMulti, 0.7), trials, up, 1.8) line 69

this has been used to test the original method
new RoutePayment(new SplitAndAdjustSize(speedyMulti), trials, up, 1.8) line 70

modified Series.generate(net, m, 5); line 73
-------------------------------------------------------------------------------------
Modifications RoutePayment:

modified protected int totalTime = 3000; line 36
modified protected int endTime = 3000; line 37
modified protected int tInterval = 500; line 58


-------------------------------------------------------------------------------------

