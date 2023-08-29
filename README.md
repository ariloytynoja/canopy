# Canopy &nbsp; <img src="docs/canopy.png" alt="icon" width="50"/>
   
Canopy is a tool for co-estimation of phylogeny and phylogeny-aware sequence alignment. By iterating the alignment step with a guide tree estimated by an external tool (such as RAxML), Canopy improves the accuracy of both the multiple sequence alignment and the resulting phylogenetic tree. When used with PRANK, Canopy can break up the alignment task to smaller subproblems and then merge these into a complete alignment, thus parallelising the PRANK alignment algorithm. Furthermore, Canopy can infer a species tree from multi-locus data by aligning the different data sets separately and then estimating the final tree from the concatenated alignment.

Although mainly aimed for phylogeny-aware alignment with [PRANK](https://ariloytynoja.github.io/prank-msa/) and [PAGAN](https://ariloytynoja.github.io/pagan-msa/), Canopy also supports other software for the sequence alignment and merge steps and for the phylogenetic inference. See [the documentation](docs/using-canopy.md#other_software) for details.  
 

*   [Installing Canopy](docs/installing-canopy.md "Installing Canopy")
*   [Using Canopy](docs/using-canopy.md "Using Canopy")
*   [Download Canopy](files/ "Download Canopy")