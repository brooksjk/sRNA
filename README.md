# sRNA
# Getting Started
### Dependencies:
- [miRDeep2](https://github.com/rajewsky-lab/mirdeep2)
- [miRDeep2_pipeline workflow](https://github.com/TF-Chan-Lab/miRDeep2_pipeline)

## Setting up mirdeep2
After pulling the github repository for [miRDeep2](https://github.com/rajewsky-lab/mirdeep2) the installation script can be run in order to install dependencies using:

```
#pull github repo 
git clone git@github.com:rajewsky-lab/mirdeep2.git

#run installation script
perl install.pl 
````
It is also necessary to make sure when testing the miRDeep2 portions of the workflow to utilize the mirdeep2 conda environment. This can be activated using:
```
source /opt/ohpc/pub/Software/mamba-rocky/etc/profile.d/conda.sh
source /opt/ohpc/pub/Software/mamba-rocky/etc/profile.d/mamba.sh
conda activate mirdeep2
```
# Issues and Resolutions
### Removing white space from .fa file headers
Files such as mature.fa, hairpin.fa, and the collapsed read files cannot have whitespaces in the header names (those following > for each read) when used with the mirdeep2.pl script. In order to resolve this the following command was used:
```
awk '/^>/ {print $1} !/^>/ {print}' your_input.fasta > your_output.fasta
```
### Filtering mature.fa and hairpin.fa files
mirdeep2.pl needs these files to be inputed with samples from the specific organism being tested. In order to do this the files were obtained from [miRBase](https://mirbase.org/download/) and then filtered specifically for reads associated with Drosophila Melanogaster (dme) using the extract_miRNAs.pl script provided with the program as such:
```
#mature
extract_miRNAs.pl /path/to/file/mature.fa dme > path/to/file/mature_dmel.fa

#hairpin
extract_miRNAs.pl /path/to/file/hairpin.fa dme > path/to/file/hairpin_dmel.fa

#others
extract_miRNAs.pl /path/to/file/mature.fa dmo,dsi > path/to/file/mature_dmel_others.fa
```
