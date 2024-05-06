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
