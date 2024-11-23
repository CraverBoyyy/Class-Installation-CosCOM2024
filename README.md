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
  <img src="https://github.com/user-attachments/assets/d21381d5-8094-45aa-9bf0-5260ea5dd80f" height="500px"  width="1200px"   align="center" >
  </p>

### 3. Installing CLASS
  Go to `CLASS` directly via terminal. Compile `C` code and `Python` wrapper using the command
  ```Linux
  make -j
  ```
  Mac users may have to install `command line tool for xcode` by going to the site: [https://developer.apple.com/download/all/](https://developer.apple.com/download/all/) (sign in is required), click download `Command Line Tools for XCode`. Execute the command
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
