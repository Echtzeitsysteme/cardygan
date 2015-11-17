# Cardygan
## Overview
CardyGAn provides capabilities for CFM editing, automated CFM validation including anomaly detection.
CardyGAn offers the following functionality:
* **CFM editor** with textual syntax based on Xtext, and an integration of cardinality annotations into the exchange format of FeatureIDE.
* **CFM validation** for automated anomaly detection for CFM with potentially infinite configuration spaces based on a combination of ILP and SMT solvers.
* **CFM configuration engine** for staged CFM configuration.

## Installation
In Eclipse install CardyGAn via Updatesite: https://raw.githubusercontent.com/Echtzeitsysteme/cardygan/master/updatesite/

## Configure CardyGAn
### Set Solver Library path
For bound analysis CardyGAn relies either on Cplex, Gurobi 6.5 or GLPK as ILP-solvers.
For gap analysis CardyGAn currently supports smt-solver Z3.
As a requirement for usage of validation capabilties of CardyGAn one of the solvers need to be installed.
Thus, the corresponding native solver libraries need to be added to the native library path.
* To set the library path e.g. for *Gurobi* and *Z3* in *Mac OS X* invoke from the command line `export DYLD_LIBRARY_PATH=/Library/gurobi605/mac64/bin:<PATH>/z3-4.4.1-x64-osx-10.11/bin/:$DYLD_LIBRARY_PATH`

### Set Solver Used for Analysis
Per default, CardyGAn uses *Gurobi* as ILP-solver and *Z3* as SMT-solver.
If you prefer to use another solver, add a corresponding `cardygan.properties`file to the project directory containing your CFM specifications. Currently configuration parameters `CPLEX`,`GLPK`and `GUROBI`(default) are supported.

For example, to use GLPK solver with Z3 add a `cardygan.properties`file at the root of a project directory:
```
ilpSolver=GUROBI
smtSolver=Z3
```

## Tutorial
