# Class-Installation

CLASS (Cosmic Linear Anisotropy Solving System) is a numerical tool for solving the evolution of linear cosmological perturbations and for computing the cosmological observables for a given input model. CLASS is a flexible and user-friendly code that can be easily generalized to non-minimal cosmological models. CLASS was written by Julien Lesgourgues & Thomas Tram, and first released in 2011. CLASS is written in C language for each module. It comes with C++ and Python wrapper. 

For more information about CLASS can be found on the website: [http://class-code.net](http://class-code.net). The CLASS papers can be found below

- CLASS I: Overview, by J. Lesgourgues, arXiv:1104.2932 [astro-ph.IM]
- CLASS II: Approximation schemes, by D. Blas, J. Lesgourgues, T. Tram, arXiv:1104.2933 [astro-ph.CO], JCAP 1107 (2011) 034


CLASS Installation 
==================
### 1. Pre-requisites
- Mac Users
  `gcc` can be installed via [Homebrew](https://brew.sh/), following the command
  ```Linux
  brew install gcc
  ```
  Next, we must install `Cython` which can be installed via
  ```Linux
  pip install Cython
  ```

- Linux Users
  You need to have `gcc` compiler `Python`, and `Cython`. To install `gcc` use the following commands,
  ```Linux
  sudo apt update
  sudo apt upgrade
  sudo apt install gcc
  ```

  Almost every Linux distribution comes with a version of `Python` included in the default system packages, Check your `Python` version by using the following command;
  ```Linux
  python3 --version
  ```
  or
  ```Linux
  python --version
  ```
  
  In case you want a better handling of the `Python` packages download and install Miniconda or Anaconda from the following links;
  [Miniconde](https://docs.anaconda.com/miniconda/)
  [Anaconda](https://www.anaconda.com/download)
  Next to install `Cython`;
  ```Linux
  pip install Cython
  ```
  or
  ```Linux
  conda install Cython
  ```
### 2. Downloading CLASS
  We can get the lastest version of `CLASS` by downloadinbg via `git` using the command
  ```Linux
  git clone https://github.com/lesgourg/class_public.git
  ```
  We can also download `CLASS` directly from [Github](https://github.com/).
  <p align="center">  
  <img src="https://github.com/user-attachments/assets/d21381d5-8094-45aa-9bf0-5260ea5dd80f" height="500px"  width="1000px"   align="center" >
  </p>

### 3. Installing CLASS
  Go to `CLASS` directly via terminal. Compile `C` code and `Python` wrapper using the command
  ```Linux
  make -j
  ```
  Mac users may have to install `Command Line Tool for XCode` by going to the site: [https://developer.apple.com/download/all/](https://developer.apple.com/download/all/) (sign in is required), click download `Command Line Tools for XCode`. 
  <p align="center">  
  <img src="https://github.com/user-attachments/assets/ba404089-ca72-4b7f-b4d0-961290975745" height="400px"  width="800px"   align="center" >
  </p>
  Execute the command
  
  ```Linux
  ./class explanatory.ini
  ```

  to test if the `C` code installed successfully.

### 4. Setting Python wrapper
  In the `CLASS` directory, go to the `python` directory and execute the command:
  ```Linux
  python setup.py build
  python setup.py install --user
  ```
  Checking if the steps above worked fine by typing
  ```Linux
  $ python
  >>> from classy import Class
  ```

Monte Python
==================
### 1. Getting Monte Python
  MontePython can be downloaded by
  ```Linux
  git clone https://github.com/brinckmann/montepython_public.git
  ```
  You need the Python program version 2.7.x** or version 3.x**. Your Python must have ‘numpy‘ (version >= 1.4.1) and ‘Cython’. The last one is used to wrap CLASS in Python. \
  Optional: If you want to use the plotting capabilities of Monte Python fully, you also need the ‘scipy’, with interpolate, and ‘matplotlib’ modules. \
  After installation, go to the directory:
  ```Linux
  cd montepython_public
  ```
  Make a copy of the file `default.conf.template` and rename it to `default.conf` (or any name your prefer)
  ```Linux
  cp default.conf.template default.conf
  ```
  At minimum, the file `default.cof` needs one line:
  ```Linux
  path['cosmo'] = path/to/your/class_public
  ```
  Make sure that your `CLASS` directory has the same name as in the path.
  Now the code is installed. There are two main (optional) commands in `MontePython`: the first one is run, for running MCMC to generate chains, another one is info, for analysing chains. More information can be viewed by executing
  ```Linux
  python montepython/MontePython.py --help
  python montepython/MontePython.py run --help
  python montepython/MontePython.py info --help
  ```
  To test a small running, executing:
  ```Linux
  path['cosmo'] = path/to/your/class_public
  ```
  To get running, type:
  ```Linux
  python montepython/MontePython.py run -o test -p example.param
  ```
  If the directory `test/` doesn’t exist, it will be created, and a run with the number of steps described in `example.param` will be started. To run a chain with more steps, one can type:
  ```Linux
  python montepython/MontePython.py run -o test -p example.param -N 100
  ```
  To analyse the chains, type
  ```Linux
  python montepython/MontePython.py info test/
  ```
  For more information, see [https://baudren.github.io/montepython.html](https://baudren.github.io/montepython.html). The documentation can be found in this link. \
  The MontePython papers can be found as
  - Brinckmann, T. and Lesgourgues, J., “MontePython 3: Boosted MCMC sampler and other features”, Physics of the Dark Universe, vol. 24, 2019. [doi:10.1016/j.dark.2018.100260](https://www.sciencedirect.com/science/article/abs/pii/S2212686418302309).
  - Audren, B., Lesgourgues, J., Benabed, K., and Prunet, S., “Conservative constraints on early cosmology with MONTE PYTHON”, Journal of Cosmology and Astroparticle Physics, vol. 2013, no. 2, 2013. [doi:10.1088/1475-7516/2013/02/001](https://iopscience.iop.org/article/10.1088/1475-7516/2013/02/001).

