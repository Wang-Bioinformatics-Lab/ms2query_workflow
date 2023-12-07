# ms2query Nextflow

To test the workflow the next command should be executed:
Take into accont that the nextflow in GNPS2 is never downloading the last models by the user. It is maintained by the Wang Bionformatics lab members. 

```
make run [-e --spectra ${spectra_path} --library ${library_path} --ionmode (positive/negative) ${ion_mode} --additional_metadata ${additional_metadata}]
```

For documentation about the ms2query tool, please read the ms2query [user guide](https://github.com/iomega/ms2query/),

All the input parameters are mandatory. For using new models, please check [https://github.com/iomega/ms2query#Create-your-own-library-and-train-new-models](https://github.com/iomega/ms2query#Create-your-own-library-and-train-new-models)

To learn NextFlow checkout this documentation:

https://www.nextflow.io/docs/latest/index.html

## Parameters in nextflow 

The parameters in nextflow follow the next priority:

i. Parameters specified on the command line (--something value)
ii. Parameters provided using the -params-file option
iii. Config file specified using the -c my_config option
iv. The config file named nextflow.config in the current directory
v. The config file named nextflow.config in the workflow project directory
vi. The config file $HOME/.nextflow/config
vii. Values defined within the pipeline script itself (e.g. main.nf)

In case you wish to set your parameters directly in nextflow, please use the next syntaxis:


```
nextflow [options] ./nf_workflow.nf --spectra ${spectra_path} --library ${library_path} --ionmode (positive/negative) ${ion_mode}
```

## Run in a conda environment

To run the workflow in a conda environment, there is a configuration file [conda_env.yml](bin/conda_env.yml). This file configured the environment named ms2query-env. It can be created and activated by:

```
conda env create -f bin/conda_env.yml
conda activate ms2query-env
```


```
nextflow [options] ./nf_workflow.nf --spectra ${spectra_path} --library ${library_path} --ionmode (positive/negative) ${ion_mode} --additional_metadata ${additional_metadata} ]
```


## Deployment in GNPS2

Check [Nexftlow template instructions from Mingxun Wang](https://github.com/Wang-Bioinformatics-Lab/Nextflow_Workflow_Template)
