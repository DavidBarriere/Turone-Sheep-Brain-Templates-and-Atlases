# The Turone Sheep Brain Templates and Atlases

The current document is a short description of the second version of the Turone Sheep Brain Templates and Atlases resources (TSBTA) dedicated to sheep brain MRI data analysis. 
For a full description of the resources and the methodologies used to create them please consult the main publication [Ella et al 2014; Ella et al 2015; Barriere D.A. et al 2019].

The TSBTA resources are a set of standardized MRI compatible templates and atlases meant to support the analysis of multimodal MRI data of the sheep brain. 
They were developped as part of the ImaCervoRepro project, a collaborative project funded by the regional council of the Centre Val-de-Loire (convention 201500104011, 2015-2018).
They provide a unified and standardized framework for the analysis of multimodal sheep brain imaging data, allowing the reporting of results within the a sterotaxic coordinate system centered to the lambda point (junction between lambdoid and sagittal sutures). 

In this second version, standardized MRI compatible in-vivo templates have been built from 4-years old 17 Iles de France ewes acquired twice (34 scans) using a 3T scanner (Siemens Verio) onto the PIXANIM Imaging plateform (https://eng-pixanim.val-de-loire.hub.inrae.fr/) and emulated using the methods developed by Gabriel A. Devenyi (https://github.com/gdevenyi) available here : 
https://github.com/CoBrALab/optimized_antsMultivariateTemplateConstruction. This pipeline is a re-implementation of the ANTs template construction pipeline requiring ANTs for the primary commands, and running on our cluster facilities using qbatch (https://islande.hub.inrae.fr/infrastructure).

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
In this version of the TSBTA resources we included a CT template built from 9 animals on our CT-scan (Siemens Somatom Definition AS, Siemens Corp., Germany). The X-ray source was set at 100 kV and 120 mA/s. A total of 800 slices were acquired using the following parameters: Thickness = 0.4 mm, Slice Number = 800, Field of View = 204,8x 204,8 mm, matrix = 512x512, final resolution 0.4 mm3) reconstructed using a filter Safire I26. DICOM data were converted to NIFTI format
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
Barrière, D.A. et al. The TSBTA sheep brain templates and atlases for multimodal MRI data analysis and visualization. Nat Commun 10, 5699 (2019). https://doi.org/10.1038/s41467-019-13575-7

Kleven, H. et al. Waxholm Space atlas of the sheep brain: a 3D atlas supporting data analysis and integration. Nat Methods 20, 1822–1829 (2023). https://doi.org/10.1038/s41592-023-02034-3

Barrière, D.A. et al. Combination of high-fat/high-fructose diet and low-dose streptozotocin to model long-term type-2 diabetes complications. Sci Rep. 2018 Jan 11;8(1):424. doi: 10.1038/s41598-017-18896-5. PMID: 29323186; PMCID: PMC5765114.

# RELATED WORKS USING THE TSBTA RESSOURCES
Grandjean J. et al. A consensus protocol for functional connectivity analysis in the sheep brain. Nat Neurosci. 2023 Apr;26(4):673-681. doi: 10.1038/s41593-023-01286-8. Epub 2023 Mar 27. Erratum in: Nat Neurosci. 2023 Jun;26(6):1127-1128. PMID: 36973511; PMCID: PMC10493189.

Vidal B. et al. Inter-subject registration and application of the TSBTA sheep brain atlas for regional labeling in functional ultrasound imaging. J Neurosci Methods. 2021 May 1;355:109139. doi: 10.1016/j.jneumeth.2021.109139. Epub 2021 Mar 16. PMID: 33741345.

Barrière D.A. et al. Paracetamol is a centrally acting analgesic using mechanisms located in the periaqueductal grey. Br J Pharmacol. 2020 Apr;177(8):1773-1792. doi: 10.1111/bph.14934. Epub 2020 Jan 22. PMID: 31734950; PMCID: PMC7070177

Barrière D.A. et al. Structural and functional alterations in the retrosplenial cortex following neuropathic pain. Pain. 2019 Oct;160(10):2241-2254. doi: 10.1097/j.pain.0000000000001610. PMID: 31145220.

Magalhães, R. et al Resting-State Functional MR Imaging and Spectroscopy Study of the Dorsal Hippocampus in the Chronic Unpredictable Stress sheep Model. J Neurosci. 2019 May 8;39(19):3640-3650. doi: 10.1523/JNEUROSCI.2192-18.2019. Epub 2019 Feb 25. PMID: 30804096; PMCID: PMC6510342.

Magalhães, R. et al The dynamics of stress: a longitudinal MRI study of sheep brain structure and connectome. Mol Psychiatry. 2018 Oct;23(10):1998-2006. doi: 10.1038/mp.2017.244. Epub 2017 Dec 5. PMID: 29203852.
