# silverman-test
It performs Silverman test for models with k peaks at a certain significance level (in python).
This is the algorithm described by [Silverman (1981)](https://ui.adsabs.harvard.edu/abs/1981JRSSB..43...97S/abstract), "Using Kernel Density Estimates to investigate Multimodality" (the paper is short -- 3 pages -- and it explains the algorithm clearly).
It tests the null hypothesis H0 that the probability density underlying the data has k modes (peaks), against the hypothesis that the density has more than k peaks.

This test was used in [Beraldo e Silva et al (2021)](https://ui.adsabs.harvard.edu/abs/2021MNRAS.502..260B/abstract), to demonstrate evidence for the presence of three peaks in the pericentric distance distribution of old stars in the Solar neighborhood.

The probability returned by the test can be interpreted as the probability for the density to have more than k modes, where k is input.

The main advantage of this method is that it does not assume any specific shape for the underlying distribution(s), or for the peaks, as is the case when one performs a Gaussian Mixture Model and computes the Bayesian Information Criterion.

This test is known to be conservative, in the sense that it is not rigorous at rejecting models with k peaks.
In other words, in some cases there might be more than k statistically significant peaks, but the test still does not reject models with k peaks.
On the other hand, if the test rejects a model with k peaks, you can bet that there is in fact evidence for more peaks.

A calibrated version of this test (more rigorous at rejecting models) was developed by Hall & York (2001), but that was only calibrated for k=1, i.e. to test the hypothesis of a single peak vs more peaks
