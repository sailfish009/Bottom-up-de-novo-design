# Design of multiple topologies to accommodate the RSVF antigenic site IV (101F epitope) 
# 3H1L_02
The de novo designed 3H1L_02 topology accommodates the RSV antigenic site 0, a discontinuous motif consisting of a kinked alpha helix and a loop segment. The antigenic site 0 was extracted from the prefusion RSVF structure (PDB 4JHW, chain F). The epitope is defined by the binding interface with the D25 antibody. The helical segment consists of residues 196-212, and the loop segment contains residues 63-69.  
In the designed connectivity, the order of the two epitope segments is reversed, meaning that the helical segment (4JHW residues 196-212) correspond to residues 6-22 in 3H1L_02, and the loop segment (4JHW residues 63-69) correspond to residues 51-57. In order to pre-stabilize the epitope, we extended the helical segment by an additional helical turn at the N-terminus, as well as by  1.5 helical turns at the N-terminus of the loop segment, as reported previously (https://doi.org/10.1101/685867). The extended site 0 epitope can be inspected [here](./site0_extended_epi.pdb). 
The topology was assembled using TopoBuilder using these [configuration/input files](./input_files). After folding and design using Rosetta FunFolDes, the best designs were filtered according to overall energy, core packing and ramachandran scores, and the best scoring decoys were inspected manually. 
For experimental testing, we designed a combinatorial library sampling a defined diversity in 12 critical core positions, as detailed [here](./B1H_A1H_B2E_A2H/output/). 
The library was screened using yeast surface display followed by next-generation sequencing, followed by recombinant expression and biophysical characterization of 13 selected clones. 

The computational models of the sequences with the strongest enrichments can be found [here](./output/pdb_files_of_best_models). All protein sequences and their computed enrichments under selection for binding to D25, 5C4, or D25+chymotrypsin / 5C4 + chymotrypsin can be found [here](./B1H_A1H_B2E_A2H/output/3H1L_02_sequences_enrichment.csv). 

# 3E2H folding and design 
Using the provided input files, the 3H1L_02 topology was built and folded using Rosetta FunFolDes, generating approximately 20,000 [decoys](./4hb_folding_design_scores.csv). The top 100 decoys were selected according to overall Rosetta energy. 
Following manual inspection, we remodeled and shortened the connecting loops between the different helices, in particular between residues 22-25, 41-47 and 60-67 by a total of 4 residues. The shortened template subsequently served as template for a second round of folding and constrained sequence design using the provided script. Based on an ensemble of the 50 best decoys according to total energy, we selected 12 core positions, including 4 potential positions for disulfide formation, and built a sequence library for combinatorial sampling of a restricted set of amino acids for the selected positions. 

# 3H1L_02 library design and testing 
| Position| AA to sample|
| :------:|:-----------:|
| 29      | EL          |
| 39      | MLA         |
| 42      | CT          |
| 45      | AVILMFW     | 
| 46      | CD          | 
| 49      | MLFIW       | 
| 66      | AVILMFW     | 
| 69      | AVILMFW     |
| 73      | AVILMFW     |
| 74      | CR          | 
| 76      | QAVLMFW     |
| 80      | ACIFW       |

The following animation shows the best scoring decoy, which was chosen as a template to select critical core positions for combinatorial sampling. Selected positions encoded in the combinatorial library are highlighted in yellow, the site 0 epitope shown in purple. 