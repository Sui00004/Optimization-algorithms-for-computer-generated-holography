<p align="center">
<img src="https://github.com/Sui00004/Optimization-algorithms-for-computer-generated-holography/blob/main/1_CGH.jpg", height="300">
</p>

## CGH Optimization
> Non-convex optimization algorithms to synthesize computer-generated holograms

Computer-generated holography (CGH) involves computationally generating a hologram and optically reconstructing an object's wavefront, which provides an approach to digitally modulate a volumetric wavefront. 

Computer-generated holograms can be encoded on various types of holographic media, including diffractive optical elements, metasurfaces, and spatial light modulators. Even so, the algorithms for hologram synthesis can be universally applied. Existing optimization frameworks applied to CGH can be conlcluded with following categories: alternative projections, the first-order gradient descent, and the second-order gradient descent.

<p align="center">
<img src="https://github.com/Sui00004/Optimization-algorithms-for-computer-generated-holography/blob/main/2_Frameworks.jpg", height="230">
</p>

Codes to achive hologram sythesis with these optmization frameworks is provided here. The algorithms to realize functional hologram sythesis using different frameworks are written in MATLAB. If you use any of these codes, please cite it as follows:

> Sui X, He Z, Chu D, & Cao L. Non-convex Optimization for Inverse Problem Solving in Computer-generated Holography. Light: Science & Applications, 29(2), 2597-2612 (2024) pp. 103-110. [[link](https://opg.optica.org/oe/fulltext.cfm?uri=oe-29-2-2597&id=446599)] [[bibtex](Inverse_CGH.bib)]

### Alternating projections
Alternative projections can be achieved by a pair of elementary projections repeatedly occurring in the optimization, which construct an iterative computation loop. Specially for CGH, alternating projections are applied to two enclosed sets associated with potential object solutions and potential hologram solutions. 

* Gerchberg-Saxton (GS) algorithm: [[2D optmizatio (phase-only hologram)](https://github.com/Sui00004/Optimization-algorithms-for-computer-generated-holography/blob/main/Alternative%20projection/Main1_GS_2D_FFT_POH.m)]
* Iterative Fourier-transform algorithm (IFTA): [[2D optmization (phase-only hologram)](https://github.com/Sui00004/Optimization-algorithms-for-computer-generated-holography/blob/main/Alternative%20projection/Main2_IFTA_2D_FFT_POH.m)], [[2D optmization with signal windows (phase-only hologram)](https://github.com/Sui00004/Optimization-algorithms-for-computer-generated-holography/blob/main/Alternative%20projection/Main3_IFTA_2D_signalwindow_FFT_2D_POH.m)], [[2D optmization with soft encoding (phase-only hologram)](https://github.com/Sui00004/Optimization-algorithms-for-computer-generated-holography/blob/main/Alternative%20projection/Main4_IFTA_2D_soft_encoding_FFT_2D_POH.m)].
* Iterative algorithm with angular spectrum theory:  [[2D optmization (complex hologram)](https://github.com/Sui00004/Optimization-algorithms-for-computer-generated-holography/blob/main/Alternative%20projection/Main5_IFTA_2D_Angularspectrum_CH.m)], [[2D optmization (phase-only hologram)](https://github.com/Sui00004/Optimization-algorithms-for-computer-generated-holography/blob/main/Alternative%20projection/Main6_IFTA_2D_Angularspectrum_POH.m)].

### First-order gradient descent
The inverse problem of hologram synthesis in CGH can also be cast as the optimization of a parameterized objective function requiring minimization with respect to its parameters. Since the choice of the objective function is often stochastic and differentiable with respect to its parameters, stochastic gradient descent (SGD) is considered as an efficient and effective first-order gradient descent framework for optimization. 

* Stochastic gradient descent (SGD) with single Fourier-transform propagation: [[2D optmization (complex hologram)](https://github.com/Sui00004/Optimization-algorithms-for-computer-generated-holography/blob/main/SGD/Main2_SGD_2D_FFT_CH.m)], [[2D optmizatio (phase-only hologram)](https://github.com/Sui00004/Optimization-algorithms-for-computer-generated-holography/blob/main/SGD/Main1_SGD_2D_FFT_POH.m)] 
* Stochastic gradient descent (SGD) with angular spectrum theory: [[2D optmization (complex hologram)](https://github.com/Sui00004/Optimization-algorithms-for-computer-generated-holography/blob/main/SGD/Main4_SGD_2D_Angularspectrum_CH.m)], [[2D optmizatio (phase-only hologram)](https://github.com/Sui00004/Optimization-algorithms-for-computer-generated-holography/blob/main/SGD/Main3_SGD_2D_Angularspectrum_POH.m)]

### Second-order gradient descent
The second-order gradient descent is implemented by the quasi-Newton method here, which minimizes the loss function by constructing and storing a series of matrices that approximate the Hessian or inverse Hessian matrix of the loss function. 

* The quasi-Newton method with single Fourier-transform propagation: [[2D optmization (complex hologram)](https://github.com/Sui00004/Optimization-algorithms-for-computer-generated-holography/blob/main/Quasi-Newton/Main2_quasiNewton_2D_FFT_CH.m)], [[2D optmizatio (phase-only hologram)](https://github.com/Sui00004/Optimization-algorithms-for-computer-generated-holography/blob/main/Quasi-Newton/Main1_quasiNewton_2D_FFT_POH.m)] 
* Stochastic gradient descent (SGD) with angular spectrum theory: [[2D optmization (complex hologram)](https://github.com/Sui00004/Optimization-algorithms-for-computer-generated-holography/blob/main/Quasi-Newton/Main4_quasiNewton_2D_Angularspectrum_CH.m)], [[2D optmizatio (phase-only hologram)](https://github.com/Sui00004/Optimization-algorithms-for-computer-generated-holography/blob/main/Quasi-Newton/Main3_quasiNewton_2D_Angularspectrum_POH.m)]

### Optmization for 3D holograms

In MATLAB, remember to add CELES to your search path with
```matlab
addpath(genpath('path/to/celes/src'));
```

As an example input you can execute the `CELES_MAIN` script. Comments in the script explain how the simulation parameters are specified. Alternatively, you can use the `CELES_model_wizard` app, a GUI that helps in the specification of the simulation parameters.

For more information, please refer to the
[documentation](https://disordered-photonics.github.io/celes/).

### Contributing
If you add any improvement or implement new features to the software please consider contributing them following the [GitHub flow](https://guides.github.com/introduction/flow/)

1. Fork the project
2. Create your feature branch: `git checkout -b my-new-feature`
3. Commit your changes: `git commit -am 'Add some feature'`
4. Push the branch: `git push origin my-new-feature`
5. Submit a [Pull request](https://github.com/disordered-photonics/celes/pulls)

If you have questions, bug reports or feature requests, please use the [Issues](https://github.com/disordered-photonics/celes/issues) section to report them.

### License
This software is published under the BSD 3-clause license, please read the [LICENSE](LICENSE) file for more information.

### Credits
CELES was initiated by Amos Egel, Lorenzo Pattelli and Giacomo Mazzamuto. In addition, Alan Zhan and Taylor Fryett have contributed code to the project. 
We thank Yasuhiko Okada and Aso Rahimzadegan for valuable comments and bug reports.

CELES uses the following codes from other programmers:
* [polarplot3d](https://it.mathworks.com/matlabcentral/fileexchange/13200-3d-polar-plot/content/polarplot3d.m) from Kenn Gerard
* [wigner3j](https://it.mathworks.com/matlabcentral/fileexchange/20619-wigner3j-symbol) from Kobi Kraus
* Iterative solvers based on the [Templates for the Solution of Linear Systems](http://it.mathworks.com/matlabcentral/fileexchange/2158-templates-for-the-solution-of-linear-systems)
