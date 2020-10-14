[![Abcdspec-compliant](https://img.shields.io/badge/ABCD_Spec-v1.1-green.svg)](https://github.com/brain-life/abcd-spec)
[![Run on Brainlife.io](https://img.shields.io/badge/Brainlife-bl.app.346-blue.svg)](https://doi.org/10.25663/brainlife.app.346)

# app-pynets
A Reproducible post-processing workflow for Structural and Functional Connectome Ensemble Learning. PyNets leverages Nilearn and Dipy fMRI and dMRI libraries to specify any of a variety of methodological choices and sampling individual structural and functional connectome estimates. PyNets is a post-processing workflow, which means that it can be run manually on virtually any preprocessed fMRI or dMRI data.

### Authors
- Derek Pisner (dpisner@utexas.edu)

### Contributors
- Soichi Hayashi (hayashis@iu.edu)
- Giulia Bertò (giulia.berto.4@gmail.com)

### Funding Acknowledgement
brainlife.io is publicly funded and for the sustainability of the project it is helpful to Acknowledge the use of the platform. We kindly ask that you acknowledge the funding below in your publications and code reusing this code.

[![NSF-BCS-1734853](https://img.shields.io/badge/NSF_BCS-1734853-blue.svg)](https://nsf.gov/awardsearch/showAward?AWD_ID=1734853)
[![NSF-BCS-1636893](https://img.shields.io/badge/NSF_BCS-1636893-blue.svg)](https://nsf.gov/awardsearch/showAward?AWD_ID=1636893)
[![NSF-ACI-1916518](https://img.shields.io/badge/NSF_ACI-1916518-blue.svg)](https://nsf.gov/awardsearch/showAward?AWD_ID=1916518)
[![NSF-IIS-1912270](https://img.shields.io/badge/NSF_IIS-1912270-blue.svg)](https://nsf.gov/awardsearch/showAward?AWD_ID=1912270)
[![NIH-NIBIB-R01EB029272](https://img.shields.io/badge/NIH_NIBIB-R01EB029272-green.svg)](https://grantome.com/grant/NIH/R01-EB029272-01)

### References
[PyNets](https://pynets.readthedocs.io/) 

### Citations
A manuscript is in preparation, but for now, please cite all uses with the following entry: 

Pisner, D., Hammonds R. (2020) PyNets: A Reproducible Workflow for Structural and Functional Connectome Ensemble Learning. Poster session presented at the 26th Annual Meeting of the Organization for Human Brain Mapping. https://github.com/dPys/PyNets.

## Running the App 
### On Brainlife.io
You can submit this App online at [https://doi.org/10.25663/bl.app.392](https://doi.org/10.25663/bl.app.392) via the "Execute" tab.

Inputs: \
This App run the multimodal workflow, i.e. both Structural and Functional Connectome Ensemble Learning. The mandatory inputs are:
* a T1w anatomical image (can be preprocessed using any method, but should be in its native scanner anatomical space)
* a BOLD/EPI series (can be preprocessed using any method, but should in the same scanner anatomical space as the T1w)
* a DWI series (should ideally be in its native diffusion MRI (dMRI) space (though can also be co-registered to the T1w image) and must contain at least one B0 for reference)

PyNets is a post-processing workflow which means that input files should already be preprocessed. Minimally, all DWI, BOLD, and T1W image inputs should be motion-corrected (and ideally also susceptibility-corrected + denoised). 

Other optional inputs are: confound regressors, brain mask, parcellation, and binarized Regions of Interest (ROIs).  

Outputs: \
At the moment, the output is an unstructured dataset containing all the output files [ADD MORE INFO ABOUT OUTPUTS HERE]. 

### Running Locally (on your machine)
1. git clone this repo.
2. Inside the cloned directory, create `config.json` with something like the following content with paths to your input files.

```json
{
        "anat": "./input/anat/t1.nii.gz",
	"task": "./input/func/bold.nii.gz",
	"dwi": "./input/dwi/dwi.nii.gz",
	"bvecs": "./input/bvecs/dwi.bvecs",
	"bvals": "./input/bva;s/dwi.bvals",
}
```

3. Launch the App by executing `main`

```bash
./main
```

### Output
The main output of this App is [ADD MORE INFO ABOUT OUTPUTS HERE].

### Dependencies
This App only requires [singularity](https://www.sylabs.io/singularity/) to run. If you don't have singularity, you will need to install following dependencies: [ADD INFO HERE].

#### MIT Copyright (c) 2020 Derek Pisner
