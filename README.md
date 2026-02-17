# CP-PAW Tutorial

This repository contains scripts and input files for the exercises in the paper

*The CP-PAW code package for first-principles calculations from a user’s perspective* 

by Peter E. Blöchl, Robert Schade, Lukas Allen-Rump, Sangeeta Rajpurohit, Amrith Rathnakaran, Konstantin Tamoev, Mani Lokamani, and Thomas D. Kühne.

## Overview

The tutorial demonstrates three main example systems using the CP-PAW method:
- **Malonaldehyde (C₃O₂H₄)** - Organic molecule with intramolecular proton transfer
- **Iron (Fe)** - BCC ferrite and hexagonal ferrum phase transitions
- **PMO (PrMnO₃)** - Praseodymium manganese oxide perovskite

## Directory Structure

```
src/
├── doall              # Master script to run all calculations
├── doit_analyze       # Post-processing and figure generation
├── doit_iron          # Iron calculations workflow
├── doit_malo          # Malonaldehyde calculations workflow
├── doit_pmo           # PMO calculations workflow
├── Iron/              # Iron system input files
├── Malo/              # Malonaldehyde system input files
├── PMO/               # PMO system input files
└── Setups/            # Atomic setup files for elements
```

## Requirements

- CP-PAW installation with parallel execution (`MPI`)
- `xmgrace` or `gracebat` for plotting

## Usage

### Running All Calculations

From the repository root directory:

```bash
bash src/doall
```

This executes all three systems sequentially:
1. Malonaldehyde calculations
2. Iron phase transition calculations  
3. PMO calculations
4. Analysis and figure generation

> [!NOTE]  
> The simulations can be computationally intensive. We recommend running them on a machine with sufficient resources.

### Running Individual Systems

**Malonaldehyde:**
```bash
bash src/doit_malo
```

**Iron:**
```bash
bash src/doit_iron
```

**PMO (Praseodymium Manganese Oxide):**
```bash
bash src/doit_pmo
```

**Analysis and Figures:**
```bash
bash src/doit_analyze
```


<!-- ## Calculations Performed

### Malonaldehyde (C₃O₂H₄)

1. **Wave function relaxation** (`urlx`) - Electronic minimization
2. **Geometry optimization** (`rlx_1`, `rlx_2`) - Two-step structure relaxation
3. **Density of states** (`dcntl`, `dpcntl`)- Electronic structure
4. **Wave function analysis** (`analyze_1`,`wcntl`)- Orbital visualization
5. **Ab initio molecular dynamics** (`aimd`) - Proton transfer dynamics
6. **Trajectory analysis** - Bond distances and temperature evolution

**Output:**
- Distance evolution during AIMD (O-H bonds, O-O distance) (Fig5)
- Temperature evolution (total, per atom type) (Fig6)

### Iron (Fe)

1. **Wave function relaxation** (`urlx`) - Initial electronic minimization
2. **Lattice optimization** (`cell`) - Cell parameter optimization
3. **Density of states** - Electronic structure analysis
4. **Transition pressure** - Ferrite ↔ Hexaferrum phase transition
5. **Lattice scan** (`scanlat`) - Energy vs. volume for equation of state
6. **Murnaghan fit** - Bulk modulus and equilibrium volume

**Output:** 
- DOS plots for ferrite and hexaferrum (Fig7)
- Energy-volume curves (Fig8a)
- Enthalpy-volume curves at transition pressure (Fig8b)

### PMO (PrMnO₃)

1. **Wave function relaxation with orbital potential** (`urlx`) - Electronic minimization with f-electron orbital potentials
2. **Wave function relaxation without orbital potential** - Comparison run
3. **Geometry optimization** (`rlx`) - Structure relaxation
4. **Density of states** - Electronic structure of perovskite
5. **Wave function analysis** - d and f orbital visualization

**Output:**
- DOS plot showing d and f states (Fig9)

## Input File Structure

### Structure Files (`.strc`)

Define atomic positions, lattice vectors, and computational parameters:
- `!LATTICE` - Unit cell vectors
- `!ATOM` - Atomic positions
- `!KPOINTS` - k-point sampling (R=value or DIV=divisions)
- `!OCCUPATIONS` - Empty bands and spin configuration
- `@setupfile@` - Placeholder for atomic setups

### Control Files (`.cntl`)

Specify calculation type and parameters:
- `!GENERIC NSTEP` - Number of steps
- `!FOURIER EPWPSI` - Plane wave cutoff energy (Ry)
- `!PSIDYN` - Wave function dynamics (Car-Parrinello)
- `!MERMIN` - Electronic temperature and occupation

### Setup Files (`.stp`)

Atomic PAW setups in `src/Setups/`:
- `fe.stp` - Iron
- `h_.stp` - Hydrogen
- `c_.stp` - Carbon
- `o_.stp` - Oxygen
- `mn.stp` - Manganese
- `pr.stp` - Praseodymium

## Output

Calculations create working directories:
- `Malo/` - Malonaldehyde results
- `Ferrite/` and `Hexaferrum/` - Iron phase results
- `PMO/` - PMO results
- `Fig5/`, `Fig6/`, `Fig7/`, `Fig8a/`, `Fig8b/`, `Fig9/` - Generated figures

Log files:
- `log` - Iron calculation log
- `log_malo` - Malonaldehyde calculation log
- `log_pmo` - PMO calculation log
- `report.txt` - Summary of key results

## Notes

- All scripts must be called from the repository root directory
- The `paw_resolve` command substitutes template variables and setup file paths
- Checkpoints are created with `paw_checkpoint` for resuming calculations
- Energy units: Hartree (H), converted to eV as needed
- Pressure units: H/a₀³, converted to GPa (1 H/a₀³ = 29421.015697 GPa)
- Length units: Bohr (a₀) and Ångström (Å)

## References

This tutorial demonstrates practical usage of the CP-PAW method for:
- Phase transitions and equation of state calculations
- Ab initio molecular dynamics
- Strongly correlated systems (f-electron materials)
- Density of states and electronic structure analysis -->

