# Limeade

This repository is the official implementation of the paper “Limeade: Let integer molecular encoding aid”.

## Documentation
Most functionalities are demonstrated using Jupyter notebooks available in the notebooks folder.


## Basic settings
To generate molecules with `N` atoms choosing from atom list `atoms`, run this command (use `N=10` and `atoms=["C", "N", "O", "S"]` as an example):

```
Mol = MIPMol(atoms=["C", "N", "O", "S"], N_atoms=10)
```

## Set bounds
To set lower and upper bounds for each type of atom, run this command:
```
Mol.bounds_atoms(lb, ub)
```
where `lb` (and `ub`) is a list with length equal to `atoms` giving the minimal (and maximal) number of each type of atom. 

Similarly, to set bounds for number of double/triple bounds and rings, run these commands:
```
Mol.bounds_double_bonds(lb_db, ub_db)
Mol.bounds_triple_bonds(lb_tb, ub_tb)
Mol.bounds_rings(lb_r, ub_r)
```
where `lb_db` (and `ub_db`) is the minimal (and maximal) number of double bonds, `lb_tb` (and `ub_tb`) is the minimal (and maximal) number of triple bonds, `lb_r` (and `ub_r`) is the minimal (and maximal) number of double rings.

## Include/Exclude substructures
To include a given list of SMARTS strings `substructures`, run this command:
```
Mol.include_substructures(substructures)
```
To exclude a given list of SMARTS strings `substructures`, run this command:
```
Mol.exclude_substructures(substructures)
```

## Generate molecules
After providing all requirements using the aforementioned functionalities, to generate molecules satisfying those requirements, run this command:
```
mols = Mol.solve(NumSolutions)
```
where `NumSolutions` is the number of generated molecules.

## Contributors
[*Shiqiang Zhang*](https://github.com/zshiqiang). Funded by BASF SE Ludwigshafen am Rhei.

[*Christian Feldmann*](https://github.com/c-w-feldmann). Funded by BASF SE Ludwigshafen am Rhei.
