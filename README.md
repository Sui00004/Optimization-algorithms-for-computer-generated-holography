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

Codes to achive hologram sythesis with these optmization frameworks is provided here. If you use any of them, please cite it as follows:

> Sui X, He Z, Chu D, & Cao L. Non-convex Optimization for Inverse Problem Solving in Computer-generated Holography. Light: Science & Applications, 29(2), 2597-2612 (2024) pp. 103-110. [[link](https://opg.optica.org/oe/fulltext.cfm?uri=oe-29-2-2597&id=446599)] [[bibtex](doc/celes.bib)]

### Features
CELES is written in MATLAB in order to provide a user-friendly, fully scriptable interface to configure and run simulations. Its prominent features are

* massively parallel execution on CUDA-capable NVIDIA GPU hardware
* block-diagonal preconditioning for faster convergence of iterative solvers
* lookup-table approach to evaluate spherical Hankel functions
* rich output (power flux, near- and far-field distributions)
* Gaussian beam excitation
* support for polydisperse samples of spheres (thanks to Alan Zhan)
* GUI (experimental)

You can refer to the [CHANGELOG](CHANGELOG.md) for details on current and upcoming features.

### Requirements
In order to run CELES, the following software (in addition to MATLAB) should be installed on your system:
* the [CUDA toolkit](https://developer.nvidia.com/cuda-downloads) matching the `ToolkitVersion` specified when running `gpuDevice` in MATLAB.
* a [C++ compiler](https://it.mathworks.com/support/compilers.html) which is supported by MATLAB in combination with the given CUDA version.



CELES has been tested on Linux using the built-in gcc compiler and on Windows using MATLAB R2017b + CUDA 8 + MS Visual Studio 2015.

In order to fully take advantage of preconditioned iterative solvers we recommend running CELES on a workstation with sufficient RAM (~several 10GB for 10000+ scattering particles).

### Getting started
CELES can be installed via cloning the GitHub repository with
```bash
git clone https://github.com/disordered-photonics/celes.git
```
or by downloading and extracting one of the [releases](https://github.com/disordered-photonics/celes/releases). Please note that the releases do not always represent the most up to date version (see the [CHANGELOG](CHANGELOG.md) for further details).

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
