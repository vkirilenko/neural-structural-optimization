# Neural reparameterization improves structural optimization

[Stephan Hoyer](https://ai.google/research/people/StephanHoyer/),
[Jascha Sohl-Dickstein](https://ai.google/research/people/JaschaSohldickstein/), [Sam Greydanus](https://greydanus.github.io/about.html)

Paper: https://arxiv.org/abs/1909.04240

To be presented at the NeurIPS 2019 workshop on [Solving inverse problems with deep networks](https://deep-inverse.org), December 13th, 2019.

This is not an official Google project.

![Optimization example](https://github.com/google-research/neural-structural-optimization/raw/master/notebooks/movie.gif)

## Installation

### The easy way

There appears to be a bug in the initial TensorFlow 2.0 release that means the
official TensorFlow pip package doesn't work. So for now, you'll need to install
the nightly [TensorFlow build](https://www.tensorflow.org/install).

This package is experimental research code, so it isn't distiributed on the
Python package index. You'll need to clone the repository with git and install
inplace. This will automatically install all required and optional
dependencies listed below, with the exception of the optional Scikit-Sparse
package.

Putting it all together:
```
# consider creating a new virtualenv or conda environment first
pip install tf-nightly
git clone https://github.com/google-research/neural-structural-optimization.git
pip install -e neural-structural-optimization
```

You should now be able to run `import neural_structural_optimization` and
execute the example notebook.

### The hard way

Install dependencies manually or with your favorite package manager.

Required dependencies for running anything at all:

- Python 3.7
- Abseil Python
- Autograd
- NumPy
- SciPy
- Scikit-Image
- TensorFlow 2.0
- Xarray

Required dependencies for running the parallel training pipeline:

- matplotlib
- Pillow
- Apache Beam

Optional dependencies:

- [Scikit-Sparse](https://scikit-sparse.readthedocs.io/en/latest/overview.html): speeds up physics simulation by about 2x
- [NLopt](https://nlopt.readthedocs.io/): required for the MMA optimizer
- Seaborn: for the notebook.

## Usage

For examples of typical usage, see the ["Optimization Examples" notebook](https://github.com/google-research/neural-structural-optimization/blob/master/notebooks/optimization-examples.ipynb).

To reproduce the full results in the paper, run `neural_structural_optimization/pipeline.py` after modifying it to launch jobs on your [Apache Beam](https://beam.apache.org) runner of choice (by default the code uses multi-processing). Note that the total runtime is about 27k CPU hours, but that includes 100 random seed replicates.

## Bibtex

```
@misc{1909.04240,
Author = {Stephan Hoyer and Jascha Sohl-Dickstein and Sam Greydanus},
Title = {Neural reparameterization improves structural optimization},
Year = {2019},
Eprint = {arXiv:1909.04240},
}
```
