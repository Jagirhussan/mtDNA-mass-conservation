# **A DNA Mass Conservation Mechanism Underpins Cellular mtDNA Number Regulation**

## **Overview**

This repository contains the code for reproducing all figures and other results in the manuscript:

**"A DNA mass conservation mechanism underpins cellular mtDNA number regulation"** *Jagir R. Hussan, Asgeir Kobro-Flatmoen, Peter Ruoff, and Stig W. Omholt*

**Abstract**: The nucleoid, which houses mtDNA within the mitochondrial matrix, is a phase-separation-driven biomolecular condensate capable of carrying out a broad spectrum of complex functions, including DNA replication, transcription, and repair. Here, we show by data-driven computational modelling that the concept of a tightly regulated intranucleoid deoxynucleoside triphoshate (dNTP) pool explains the observation that the number of mtDNA base pairs per cell is conserved in human hybrid cell lines regardless of the size of the introduced mitochondrial genome. This concept is then used to address the enigmatic observation that the synthesis rate of the short DNA strand called 7S DNA, which is part of the triple-stranded displacement loop (D-loop) found in the main noncoding region of mtDNA, increases dramatically during the cell cycle. Collectively, our quantitative analyses suggest that the mammalian mtDNA replisome uses a strictly controlled intranucleoid dNTP pool based predominantly on intranucleoid synthesis and subsequent degradation of 7S DNA.

## **Repository Structure**

The codebase is organized into Jupyter Notebooks, each corresponding to specific analytical calculations and figures presented in the manuscript.

* **Manuscript\_calculations.ipynb** Contains code for specific calculations reported in the text not attached to figures.  
* **Figure\_1.ipynb** Implements the base agent-based Nucleoid class and the FeedbackSimulation engine. This notebook generates **Figure 1** in the paper.  
* **Figure\_2and3.ipynb** Contains the cell cycle simulation engines (SasakiSimulation and CellCycleSimulation). This notebook generates **Figures 2 and 3** in the main paper and **Figures S1 to S9** in the Supplementary material. It utilizes parallel processing to generate the data and the plots.

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
