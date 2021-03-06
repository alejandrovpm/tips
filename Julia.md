Tips for Julia
=============================
To install: <https://julialang.org/downloads/>

For ubuntu :
* Ther is not a normal installation, only download the pacage and vreate the **symbolic links**
* remember to check the ubuntu tips for the **symbolic links**

 Help
------------------
To return the documentation of a function just use: `?`

Functions
----------------------

Documentation available in: https://docs.julialang.org/en/

* Look type of a variable: `typeof()`
* Size of the array: `size()`
* Get a list of current variable `whos()`
* Concatenate strings: `"string 1" * "string 2"`
* Convert range to an array: `collect(range)`
* Broadcast an operation of a an array over a matrix: `broadcast(<+,-,/,*>,A,a)`
* For Structures go to composite types in https://docs.julialang.org/en/v0.6.4/manual/types/#man-types-1

### Multi-dimensional Arrays

 Documentation available in: https://docs.julialang.org/en/v0.6/manual/arrays/#Comprehensions-1

 #### Concatenation
 `cat(k,A)` where `k` is the dimension to be concatenated (also see `vcat(A)` and `hcat(A)`)

#### Comprehensions
I tis meant to speed up the construction of an array of 1-dimension
`A = [ F(x,y,...) for x=rx, y=ry, ... ]`



Atom
--------------------------
Integrated development environment (IDE) **Juno**

For installation: http://docs.junolab.org/latest/man/installation.html

Modules
--------------------------

To add a path of the Julia Path:
```Julia
push!(LOAD_PATH, "/Path/To/My/Module/")
```

Packages
---------------
```Julia
using Pkg
```

* To add: `Pkg.add("package")`
* To build: `Pkg.build("package")`
* To update: `Pkg.update()`

### Jupyter

Editor for

```Julia
using IJulia
notebook(detached=true)
```

more: <https://github.com/JuliaLang/IJulia.jl>


### Python

#### Install

1. `Pkg.add("PyCall")`

2. Configure **Python 2.7** in julia type:
  *Ubuntu* : `ENV["PYTHON"] = "/usr/bin/python2.7"`
  *OSX*:?

3. Build the package `Pkg.build()` and the restart Julia.

#### Using
```Julia
using PyCall
@pyimport <package>
@pyimport numpy.random as nr
@pyimport matplotlib.pyplot as plt

@pyimport math
math.sin(math.pi / 4) - sin(pi / 4)  # returns 0.0
```
To build PyCall: `Pkg.build("PyCall")`


To add local modules, in the terminal before starting julia `export PYTHONPATH="$PYTHONPATH:<path where is the local module>"`

For ubuntu: `export PYTHONPATH="$PYTHONPATH:/home/cristian/etasl_ws/src/etasl_motionmodel/scripts/python"`

more: <https://github.com/JuliaPy/PyCall.jl>

#### Recommended Python Packages

For better results install them inside python environment embedded in Julia

* `scipy`
* `numpy`
* `matpolotlib`
* `fastdtw` from `bioconda` channel


### Pyplot

Package to plot

```Julia
using PyPlot
x = linspace(0,2*pi,1000); y = sin.(3 * x + 4 * cos.(2 * x));
plot(x, y, color="red", linewidth=2.0, linestyle="--")
title("A sinusoidally modulated sinusoid")
```

more: <https://github.com/JuliaPy/PyPlot.jl>

### PlotlyJS

Neat plots

Docs: <http://spencerlyon.com/PlotlyJS.jl/>
Repo: <https://github.com/sglyon/PlotlyJS.jl>

To save in vector formats

install *Blink*: `Pkg.add("Blink"); Blink.AtomShell.install()`
install *Rsvg*: `Pkg.add("Rsvg")`
### Rsvg

To save figures in vector formats

### Conda

Binary provider for Julia. It is linked to Anaconda but more channels can be added.

```Julia
using Conda
```

* Add channels: `Conda.add_channel("my_channel")`
* Add packages: `Conda.add("package")`
more: <https://github.com/JuliaPy/Conda.jl>

### Interpolations

Interpolation and B-Splines

```Julia
using Interpolations
```
more: <https://github.com/JuliaMath/Interpolations.jl>


### Dates

Used to get TimeStamp
info: https://en.wikibooks.org/wiki/Introducing_Julia/Working_with_dates_and_times

### JSON

Package to write and read json files: https://gist.github.com/silgon/0ba43e00e0749cdf4f8d244e67cd9d6a
