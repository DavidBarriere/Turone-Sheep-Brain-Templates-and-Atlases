# The Turone Sheep Brain Templates and Atlases

The current document is a short description of the second version of the Turone Sheep Brain Templates and Atlases resources (TSBTA) dedicated to sheep brain MRI data analysis. 
For a full description of the resources and the methodologies used to create them please consult the main publication [Ella et al 2014; Ella et al 2015; Barriere D.A. et al 2019].

The TSBTA resources are a set of standardized MRI compatible templates and atlases meant to support the analysis of multimodal MRI data of the sheep brain. 
They were developped as part of the ImaCervoRepro project, a collaborative project funded by the regional council of the Centre Val-de-Loire (convention 201500104011, 2015-2018).
They provide a unified and standardized framework for the analysis of multimodal sheep brain imaging data, allowing the reporting of results within the a sterotaxic coordinate system centered to the lambda point (junction between lambdoid and sagittal sutures). 

In this second version, standardized MRI compatible in-vivo templates have been built from 4-years old 17 Iles de France ewes acquired twice (34 scans) using a 3T scanner (Siemens Verio) onto the PIXANIM Imaging plateform (https://eng-pixanim.val-de-loire.hub.inrae.fr/) and emulated using the methods developed by Gabriel A. Devenyi (https://github.com/gdevenyi) available here : 
https://github.com/CoBrALab/optimized_antsMultivariateTemplateConstruction.

This pipeline is a re-implementation of the ANTs template construction pipeline requiring ANTs for the primary commands, and running on our cluster facilities using qbatch (https://islande.hub.inrae.fr/infrastructure).

Using this methodology we firstly, updated the previous TSBTA spaces (T1, IR, T2) previously generated using the FSL and SPM and normalized the whole head images instead of brain only.

Secondly, we updated the probabilistic maps (grey matter, White matter, CSF) of the sheep brain which are mandatory for the automatic segmentation of the sheep brain and standardisation of morphometric analysis.

Thirdly, additionnal head templates (T1, IR, T2) and their associated Grey Matter, White Matter and CSF maps have been created using the optimized ANTs methodology.

Fourthly, using the same spatial normalisation strategy, we created a CT reference space using the CT data from 9 animals aquired in-vivo on our CT-scan (Siemens Somatom Definition AS, Siemens Corp., Germany) obtained onto the PIXANIM Imaging plateform which have been normalized to in vivo T1w template allowing to the TSBTA resource to propose a multimodal space for CT/MRI normalisation of sheep head/brain.

Eventually, we updated the original TSBTA atlas by adding a complete segmentation of the thalamus and additionnal regions of interest (skull, rhinocele, sinuses, etc.). The TSBTA is now composed by a mosaic of 202 ROIs embedded within a 3D sterotaxic space which can be used for the development of neuronavigation tool and surgical stereotaxic approaches in sheep. 

## Organisation of the TSBTA resources
The TSBTA resources have been organized as three main sections : Head templates, Brain templates, CT template

  ### Head templates
  In this section a set of templates, priors and brain masks is available for in-vivo data normalization.
  
  T1-weighted template (3D MPRAGE sequence) + IR T1-weighted template (3D IR-SPACE sequence) + T2-weighted (3D T2 MEDIC) + associated probabilistics maps of GM (prob01), WM (prob02) and CSF (prob03) + brain masks + brain atlas and its associated labels nomenclature at the ITKSnap format.
  
  Spatial resolution = 0.5x0.5x0.5mm.
  
  Matrix size = 288x288x384
  
      atlas_labels.txt
      atlas.nii.gz
      head_ir_template.nii.gz
      head_t1_template.nii.gz
      head_t2_template.nii.gz
      mask_brain_eroded.nii.gz
      mask_brain.nii.gz
      prob01.nii.gz
      prob02.nii.gz
      prob03.nii.gz

  ### Brain templates
  In this section a set of templates, priors and brain masks is available for in-vivo data normalization.
  
  T1-weighted template (3D MPRAGE sequence) + IR T1-weighted template (3D IR-SPACE sequence) + T2-weighted (3D T2 MEDIC) + associated probabilistics maps of GM (prob01), WM (prob02) and CSF (prob03) + brain masks + brain atlas and its associated labels nomenclature at the ITKSnap format.
  
  Spatial resolution = 0.5x0.5x0.5mm.
  
  Matrix size = 140x210x162
  
      atlas_brain.nii.gz
      atlas_labels_brain.txt
      brain_ir_template.nii.gz
      brain_t1_template.nii.gz
      brain_t2_template.nii.gz
      mask_brain_eroded.nii.gz
      mask_brain.nii.gz
      mask_brain_probability.nii.gz
      prob01.nii.gz
      prob02.nii.gz
      prob03.nii.gz



  #### CT template
In this version of the TSBTA resources we included a CT template built from 9 animals on our CT-scan (Siemens Somatom Definition AS, Siemens Corp., Germany). The X-ray source was set at 100 kV and 120 mA/s.

A total of 800 slices were acquired using the following parameters: Thickness = 0.4 mm, Slice Number = 800, Field of View = 204,8x 204,8 mm, matrix = 512x512, final resolution 0.4 mm3) reconstructed using a filter Safire I26. DICOM data were converted to NIFTI format
and CT data were spatially normalized to the TSBTA in-vivo template using the previously described methods.

Spatial resolution 0.25x0.25x0.25mm.

Matrix size = 280x420x324

      atlas.nii.gz
      atlas_labels.txt
      ct.nii.gz
      t1.nii.gz

## Important Note
TSBTA ressources are provided at the scanner resolution and are oriented in anterior commisure/posterior commisure axis. Center of the images have been set at the posterior commisure level (Lambda 0 mm).

For any questions regarding the TSBTA ressource, please email David A. Barrière (david.barriere@cnrs.fr).

# REFERENCES

Ella A, Delgadillo JA, Chemineau P, Keller M. Computation of a high-resolution MRI 3D stereotaxic atlas of the sheep brain. J Comp Neurol. 2017 Feb 15;525(3):676-692. doi: 10.1002/cne.24079.


Ella A, Keller M. Construction of an MRI 3D high resolution sheep brain template. Magn Reson Imaging. 2015 Dec;33(10):1329-1337. doi: 10.1016/j.mri.2015.09.001.



# RELATED WORKS USING THE TSBTA RESSOURCES

Murray SJ, Almuqbel MM, Felton SA, Palmer NJ, Myall DJ, Shoorangiz R, Ella A, Keller M, Palmer DN, Melzer TR, Mitchell NL. Progressive MRI brain volume changes in ovine models of CLN5 and CLN6 neuronal ceroid lipofuscinosis. Brain Commun. 2023 Jan 2;5(1):fcac339. doi: 10.1093/braincomms/fcac339.


Barrière DA, Ella A, Adriaensen H, Roselli CE, Chemineau P, Keller M. In vivo magnetic resonance imaging reveals the effect of gonadal hormones on morphological and functional brain sexual dimorphisms in adult sheep. Psychoneuroendocrinology. 2019 Nov;109:104387. doi: 10.1016/j.psyneuen.2019.104387.


Nelvagal HR, Eaton SL, Wang SH, Eultgen EM, Takahashi K, Le SQ, Nesbitt R, Dearborn JT, Siano N, Puhl AC, Dickson PI, Thompson G, Murdoch F, Brennan PM, Gray M, Greenhalgh SN, Tennant P, Gregson R, Clutton E, Nixon J, Proudfoot C, Guido S, Lillico SG, Whitelaw CBA, Lu JY, Hofmann SL, Ekins S, Sands MS, Wishart TM, Cooper JD. Cross-species efficacy of enzyme replacement therapy for CLN1 disease in mice and sheep. J Clin Invest. 2022 Oct 17;132(20):e163107. doi: 10.1172/JCI163107.


Russell KN, Mitchell NL, Anderson NG, Bunt CR, Wellby MP, Melzer TR, Barrell GK, Palmer DN. Computed tomography provides enhanced techniques for longitudinal monitoring of progressive intracranial volume loss associated with regional neurodegeneration in ovine neuronal ceroid lipofuscinoses. Brain Behav. 2018 Sep;8(9):e01096. doi: 10.1002/brb3.1096.
