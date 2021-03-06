# mesowest: Simple R functions for working with the Mesowest / SynopticLabs climate data API


## Installation

```
library(devtools)
install_github('fickse/mesowest')
```

## Authentication

After you have obtained an [API key](https://synopticlabs.org/api/guides/?getstarted), request a token...

```r
library(mesowest)

requestToken(apikey = "YoUrApIkEY918202s")

# or interactively choose a text file with the key...
requestToken()

``` 
The token is saved to a text file in your root directory (`~/`)

## Getting data

Services are accessed through the function `mesowest::mw`
Parameters can be input as named arguments 

```r
mw(service = 'metadata', complete=1, state='UT', county='Garfield')

```  
If this results in awkward nested dataframes, include `jsonsimplify = FALSE` as an argument.  


A quick reference for parameters can be accessed with `getparams()`

```r
# all parameters for all services
getparams()

# parameters for a specific service
getparams('networks')
```

There is also a shortcut api call to list variables

```r
mwvariables()
```

---

Note: This package was created independently from SynopticLabs, MesoWest, or any associates. It is intended to be used for research purposes only.
