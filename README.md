# Ligand-Based Pocket Finding and Docking Framework

A lightweight framework for identifying protein binding pockets and performing molecular docking with ligands.

## Features

- Protein structure preprocessing
- Binding pocket identification and ranking
- Ligand preparation and conformer generation
- Molecular docking with configurable parameters
- Results analysis and visualization
- Easy configuration through a single config file

## Installation

### Prerequisites

- Python 3.8 or higher
- RDKit
- BioPython
- NumPy, SciPy, Matplotlib
- Optional: Open Babel, PyMOL (for visualization)
- AutoDock Vina or another docking engine

### Setup

1. Clone this repository:
   ```
   git clone https://github.com/username/ligand-docking-framework.git
   cd ligand-docking-framework
   ```

2. Create a virtual environment (recommended):
   ```
   python -m venv venv
   source venv/bin/activate  # On Windows: venv\Scripts\activate
   ```

3. Install the dependencies:
   ```
   pip install -r requirements.txt
   ```

4. Install RDKit (if not installed via pip):
   ```
   conda install -c conda-forge rdkit
   ```

5. Install a docking engine:
   - AutoDock Vina: Download from http://vina.scripps.edu/
   - Add the executable to your PATH

## Usage

### Basic Usage

Run the example script with your protein and ligand files:

```bash
python docking_example.py -p your_protein.pdb -l your_ligand.sdf -o results_directory
```

### Command Line Arguments

- `-p`, `--protein`: Path to protein structure file (PDB format)
- `-l`, `--ligand`: Path to ligand file (SDF, MOL, or MOL2 format)
- `-o`, `--output`: Output directory for results (default: docking_results)
- `--skip-prep`: Skip protein preprocessing if already done
- `--use-pocket`: Use specific pocket by index (0=top ranked)

### Configuration

Edit the `config.py` file to customize parameters for:

- Protein preprocessing
- Pocket finding
- Ligand preparation
- Docking parameters
- Results analysis

## Example Workflow

1. **Protein Preparation**:
   - Remove water molecules and non-standard residues
   - Add hydrogens at physiological pH
   - Optimize hydrogen positions

2. **Pocket Finding**:
   - Calculate protein surface
   - Identify potential binding cavities
   - Rank pockets by size, druggability, or other metrics

3. **Ligand Preparation**:
   - Add hydrogens and generate 3D conformers
   - Assign proper protonation states
   - Generate multiple conformations

4. **Docking**:
   - Define search box around selected pocket
   - Perform docking with selected engine
   - Generate and score binding poses

5. **Analysis**:
   - Calculate protein-ligand interactions
   - Visualize binding modes
   - Generate docking report

## Extending the Framework

### Adding a New Pocket Finding Algorithm

1. Modify the `PocketFinder` class in `ligand_docking_framework.py`
2. Implement your algorithm in the `identify_cavities` method

### Adding a New Docking Engine

1. Modify the `Docking` class in `ligand_docking_framework.py`
2. Implement the interface to your docking engine in `dock_to_pocket`

## Future Improvements

- Integration with MD simulation tools
- Machine learning-based pocket scoring
- Web interface for visualization and analysis
- Support for ensemble docking

## License

Personal code

## Citation

If you use this framework in your research, please cite:

```
Uma-Lakshmi Dakshinamoorthy. (2025). Ligand-Based Pocket Finding and Docking Framework. GitHub repository. https://[github.com/username/ligand-docking-framework](https://github.com/Uma-Dakshinamoorthy/Simple-Docking-/)
```
