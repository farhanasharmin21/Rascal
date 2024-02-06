# RascalC
**A Rapid Sampler For Large Cross-Covariance Matrices in C++**

C++ code to simulate correlation function covariance matrices from large surveys, using a grid and jackknife based approach. This can be used to find covariances of (a) the angularly binned anisotropic 2PCF, (b) the Legendre-binned anisotropic 2PCF and (c) the Legendre-binned isotropic 3PCF in arbitrary survey geometries. For (a) we can also compute the jackknife covariance matrix, which can be used to fit our non-Gaussianity model. There is additionally functionality to compute multi-tracer cross-covariances for the 2PCF.

For full usage, see the ReadTheDocs [documentation](https://rascalc.readthedocs.io/en/latest).

Any usage of this code should cite [Philcox et al. 2019](https://arxiv.org/abs/1904.11070) (for the angularly binned 2PCF) and [Philcox & Eisenstein 2019](https://arxiv.org/abs/1910.04764) (for the Legendre-binned 2PCF and 3PCF).

***New for version 2***: Legendre moment covariances and the 3PCF

## Python interface (alpha-testing before version 3.0)

### Installation for DESI members at NERSC

```
cd /global/common/software/desi/users/mrash/RascalC
pip install -e .
```
This installs the library from my software folder in the development mode, so that after I update it e.g. with some fix, you will have the new version without the need to re-install.

### Generic installation (if the above is unavailable)

```
git clone https://github.com/misharash/RascalC
cd RascalC
pip install -e .
```
This installs the in development mode, so that when you pull the code updates, they are reflected immediately.
At this stage, the fixes might be required pretty often.

### Very minimal usage guide

```
import RascalC
result = RascalC.run_cov(...)
```

`run_cov` is the main function for the covariance matrix computation.
Use `help(RascalC.run_cov)` to learn more about the inputs; many of them are similar to [pycorr](https://github.com/cosmodesi/pycorr) `TwoPointCorrelationFunction` and some others are `pycorr.TwoPointEstimator`s.

More documentation is coming, in the meantime please contact Michael 'Misha' Rashkovetskyi <mrashkovetskyi@cfa.harvard.edu> with any questions.
Please also feel free to open [GitHub issues](https://github.com/misharash/RascalC/issues) both for problems and clarification requests.

## Authors

- Oliver Philcox (Columbia / Simons Foundation)
- Daniel Eisenstein (Harvard)
- Ross O'Connell (Pittsburgh)
- Alexander Wiegand (Garching)
- Misha Rashkovetskyi (Harvard)

We thank Yuting Wang and Ryuichiro Hada for pointing out and fixing a number of issues with the code and its documentation. We are particularly grateful to Uendert Andrade for finding a wide variety of improvements and bugs!
