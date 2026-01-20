# CP-PAW Tutorial

This repository contains scripts and input files for the exercises in the paper
*The CP-PAW code package for first-principles calculations from a user’s perspective* by Peter E. Blöchl, Robert Schade, Lukas Allen-Rump, Sangeeta Rajpurohit, Amrith Rathnakaran, Konstantin Tamoev, Mani Lokamani, and Thomas D. Kühne.

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