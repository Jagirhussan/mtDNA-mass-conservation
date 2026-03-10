# **A DNA Mass Conservation Mechanism Underpins Cellular mtDNA Number Regulation**

## **Overview**

This repository contains the official computational models and analysis code for the manuscript:

**"A DNA mass conservation mechanism underpins cellular mtDNA number regulation"** *Jagir R. Hussan, Asgeir Kobro-Flatmoen, Peter Ruoff, and Stig W. Omholt*

The nucleoid, which houses mitochondrial DNA (mtDNA) within the mitochondrial matrix, operates as a phase-separation-driven biomolecular condensate. The computational framework provided in this repository tests the hypothesis that a tightly regulated intranucleoid deoxynucleoside triphosphate (dNTP) pool governs mtDNA mass conservation.

By employing a hybrid continuous/discrete-event simulation framework, this repository demonstrates how dNTP pool regulation accounts for:

1. Homeostasis of cellular mtDNA numbers in postmitotic cells.  
2. The temporal increase of nucleoids during the cell cycle.  
3. The conservation of mtDNA mass, irrespective of the introduced mitochondrial genome size (e.g., wild-type vs. mutant deletion lines).  
4. The kinetic dynamics and synthesis rates of 7S DNA within the D-loop.

## **Repository Structure**

The codebase is organized into Jupyter Notebooks, each corresponding to specific analytical calculations and figures presented in the manuscript.

* **Manuscript\_calculations.ipynb** Contains the foundational analytical calculations discussed in the text, including the biological constants, the energetic (ATP) cost analysis for *de novo* dNTP synthesis, and the HeLa cell 7S DNA residence time calculations.  
* **Figure\_1.ipynb** Implements the base agent-based Nucleoid class and the FeedbackSimulation engine. This notebook generates **Figure 1**, demonstrating postmitotic nucleoidstasis driven by feedback-regulated dNTP supply (Equation 1).  
* **Figure\_2and3.ipynb** Contains the advanced cell cycle simulation engines (SasakiSimulation and CellCycleSimulation). This notebook explores replication rules, inheritance, and mass conservation across different genome sizes (16,569 bp, 25,323 bp, and 9,049 bp). It utilizes parallel processing to generate the data and plots for **Figures 2, 3 and supplementary figures**.

## **System Requirements and Installation**

### **Prerequisites**

The simulations rely on standard scientific Python libraries, as well as dask for parallel execution of stochastic replicates.

* Python \>= 3.9  
* NumPy  
* SciPy  
* Matplotlib  
* Dask  
* JupyterLab / Jupyter Notebook

### **Setup Instructions**

It is recommended to run this code within an isolated virtual environment (e.g., using conda or venv).

\# Clone the repository  
git clone [https://github.com/Jagirhussan/mtDNA-mass-conservation.git](https://github.com/Jagirhussan/mtDNA-mass-conservation.git)  
cd mtDNA-mass-conservation

\# Create a virtual environment (using venv)  
python3 \-m venv venv  
source venv/bin/activate  \# On Windows: venv\\Scripts\\activate

\# Install required dependencies  
pip install numpy scipy matplotlib dask\[complete\] jupyterlab

## **Usage and Execution**

To reproduce the findings from the manuscript, launch Jupyter Lab and execute the notebooks in sequential order:

jupyter lab

**Note on Computational Cost:** Stochastic simulations, particularly those in Figure\_2and3.ipynb, rely on a high number of replicates to ensure statistical robustness. The code utilizes dask.bag for parallelization. Execution times will vary depending on your local machine's multi-core processing capabilities. Cached results are saved to a figures/ directory to prevent redundant computation on subsequent runs.

## **Citation**

If you utilize this code or model in your research, please cite the original manuscript:

@article{Hussan202X,  
  title={A DNA mass conservation mechanism underpins cellular mtDNA number regulation},  
  author={Hussan, Jagir R. and Kobro-Flatmoen, Asgeir and Ruoff, Peter and Omholt, Stig W.},  
  journal={\[Journal Name\]},  
  year={\[Year\]},  
  doi={\[DOI\]}  
}

## **License**

This project is licensed under the MIT License \- see the [LICENSE](http://docs.google.com/LICENSE) file for details.