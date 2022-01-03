# A short introduction to julia

This repo is an addition to my bachelor's thesis in which I, used the julia programming language to simulate a set of fast oscillating ode's.
Since MATLAB is the predominantly used language by most academics in this space, I think it is appropriate to provide a little introduction for this fairly new language (the 1.0 release was on 08.08.2018).

## Benefits of julia
I have compiled a list of things I find particularly interesting or noteworthy about julia in the julia_intro.ipynb notebook.
But first I want to give a broad overview about the language the tools used and how to install them.

### Performance

The reasons why I chose julia over MATLAB were the latter one's slow performance and limited feature set, when it comes to numerical solutions to differential equation systems. Whereas in Matlab an average simulation run passed the 20 min mark, I could complete the same simulation in julia in about 3 seconds, which is a 400x increase in speed. This extreme performance increase is however not reached across the board.

![[Performance comparison with other languages](https://julialang.org/benchmarks)](https://julialang.org/assets/benchmarks/benchmarks.svg)
But as you can see in the above graphic, the performance is quite solid, especially compared to other high level languages like Python or MATLAB.

The reason for its speed is the use of a just-in-time-compiler (JIT). Julia code gets compiled down to binary on first execution. This leads to a slower first execution, but C-like speeds after that. A similar process is used by modern JavaScript interpreters, like in Chrome (V8) or Firefox (spidermonkey).

### Development and Community
Julia is a community driven and developed language. The initial goal was to create a language that was easy, fast and versatile. The initial group of contributors is located at MIT but with growing popularity many more people contributed to the core language and especially community made packages.
By leveraging the community, julia has number of high quality libraries like the [DifferentialEquations.jl](https://diffeq.sciml.ai/stable/), [JuMP (for mathematical optimizations)](https://jump.dev/) or [Plots.jl](https://github.com/JuliaPlots/Plots.jl). A curated list of packages can be found [here](https://github.com/svaksha/Julia.jl).
In addition one finds a very active and welcoming [forum](https://discourse.julialang.org/) and a good [documentation](https://docs.julialang.org)

## Tooling
The interactive terminal julia session is called the [REPL (read-eval-print-loop)](https://docs.julialang.org/en/v1/stdlib/REPL/). I would recommend using the repl mainly to install packages and launch scripts.
My simulations and interactive sessions were done in JupyterLab.
JupyterLab or Jupyter Notebook provide an interactive notebook which can run code, but also incorporate text, images and general media or web elements.
Examples to run in the browser can be found at the [jupyter website](https://jupyter.org/). Most major languages can be used with jupyter, for example Julia, Python, MATLAB, Java Rust, Haskell, JavaScript...

Alternatively julia code and jupyter notebooks can be run in VSCode.
Note, that the VSCode julia plugin uses a custom kernel which does not provide multithreading at the moment.

## Installation

### Julia
The julia installer can be obtained at the [julia websites download page](https://julialang.org/downloads/) for all major operating systems and FreeBSD. It is of course available on pretty much any system with a package manager. On windows julia needs to be added to PATH manually if its installed with winget.
I wrote my code in julia 1.6.3 and 1.7, so this is the minimum version that should be installed. Afaik this is only a concern on debian based linux distros.

### Jupyter Notebook / JupyterLab
A short word on the differences between the two. Jupyter Notebook is the older front end for the jupyter framework. JupyterLab has more features and most importantly for development allows to show the notebook in multiple views or different notebooks at a time. Jupyter Notebook can only show one notebook at one place, but is in my experience more performant.
Jupyter is based on python and can be installed in various ways.

#### Installation via julia
Julia can install Jupyter Notebook through its own package manager.
Hit the "]" key, and you will enter the package mode.
Simply type "add IJulia" and press enter.
After the package installation which can take a few minutes, you can start Jupyter notebook by running the "notebook()" command and JupyterLab with "jupyterlab()". On the first run of this commands julia will install miniconda and add jupyter to the system through it, if no jupyter installation is found.
If you already have python with pip or conda installed i would advice to use that.

#### Installation via python
Just follow the [install guide provided by the jupyter team](https://jupyter.org/install).

## Links and Resources
- [Website](https://julialang.org/)
- [YouTube Channel](https://www.youtube.com/c/TheJuliaLanguage)
- [Forum](https://discourse.julialang.org/)
- [Cheatsheet](https://juliadocs.github.io/Julia-Cheat-Sheet/)
- [Comparison of MATLAB, Python and Julia Commands](https://cheatsheets.quantecon.org/)
- [docs](https://docs.julialang.org/en/v1/)

### Library of interest

- [Plots](https://docs.juliaplots.org/latest/tutorial/)
- [Gadfly (alternative plotting module)](http://gadflyjl.org/stable/)
- [DifferentialEquations](https://diffeq.sciml.ai/stable/)
- [Linear Algebra](https://docs.julialang.org/en/v1/stdlib/LinearAlgebra/)
- [DataFrames](https://dataframes.juliadata.org/stable/)
