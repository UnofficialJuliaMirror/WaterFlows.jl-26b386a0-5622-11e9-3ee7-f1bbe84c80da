# Vann

## Getting started

To install the package, use the following command inside the Julia REPL:

````julia

Pkg.clone("https://github.com/jmgnve/Vann2")
````




To load the package, use the command:

````julia
using Vann2
````





## Input data format

Vann currently reads data in a specific text format (see examples for [Atnasjø](https://github.com/jmgnve/Vann2/tree/master/data/atnasjo) and [Fetvatn](https://github.com/jmgnve/Vann2/tree/master/data/fetvatn)). 

First read the data for one of the example datasets, here Atnasjø:

````julia
path = joinpath(Pkg.dir("Vann2"), "data", "atnasjo")

date, tair, prec, q_obs, frac_lus, frac_area, elev = load_data(path)
````





Second, compute potential evapotranspiration for the catchment:

````julia
lat = 60.0
epot = oudin(date, tair, lat, frac_area)
````





Third, create an input object that is required for running the models:

````julia
input = InputPTE(prec, tair, epot);
````





## Using a complete model





## Building a model from components









## Available models






## Available components
