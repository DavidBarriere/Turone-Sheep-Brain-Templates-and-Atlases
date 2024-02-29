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
The TSBTA resources have been organized as two main sections : Head templates and Brain templates

  ### Head templates
  In this section a set of templates, priors and brain masks is available for ex-vivo and in-vivo data normalization.
  
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


  #### Ex-vivo diffusion
  B0 template + FA template + associated probabilistics maps (GM, WM, CSF, Skull, outbrain) + brain mask.
  
  Spatial resolution 0.25x0.25x0.25mm.
  
      SIGMA_ExVivo_Diffusion_Brain_b0.nii.gz
      SIGMA_ExVivo_Diffusion_Brain_csf.nii.gz
      SIGMA_ExVivo_Diffusion_Brain_fa.nii.gz
      SIGMA_ExVivo_Diffusion_Brain_gm.nii.gz
      SIGMA_ExVivo_Diffusion_Brain_mask.nii.gz
      SIGMA_ExVivo_Diffusion_Brain_out.nii.gz
      SIGMA_ExVivo_Diffusion_Brain_skull.nii.gz
      SIGMA_ExVivo_Diffusion_Brain_wm.nii.gz

  #### In-vivo T2-weighted
  T2-weighted template + associated probabilistics maps (GM, WM, CSF, Skull, outbrain) + brain mask.
  
  Spatial resolution 0.15x0.15x0.15mm.

      SIGMA_InVivo_Anatomical_Brain_csf.nii.gz
      SIGMA_InVivo_Anatomical_Brain_gm.nii.gz
      SIGMA_InVivo_Anatomical_Brain_mask.nii.gz
      SIGMA_InVivo_Anatomical_Brain_out.nii.gz
      SIGMA_InVivo_Anatomical_Brain_skull.nii.gz
      SIGMA_InVivo_Anatomical_Brain_template.nii.gz
      SIGMA_InVivo_Anatomical_Brain_wm.nii.gz

  #### In-vivo diffusion
  T2-weighted template + B0 template + FA template + ADC template + brain mask.
  
  Spatial resolution 0.375x0.375x0.375mm.

      SIGMA_InVivo_Diffusion_Brain_adc.nii.gz
      SIGMA_InVivo_Diffusion_Brain_b0.nii.gz
      SIGMA_InVivo_Diffusion_Brain_fa.nii.gz
      SIGMA_InVivo_Diffusion_Brain_mask.nii.gz
      SIGMA_InVivo_Diffusion_Brain_t2.nii.gz

  ### Brain templates
  T2-weighted template + associated probabilistics maps (GM, WM, CSF, Skull, outbrain) + brain mask.

  Spatial resolution 0.375x1x0.375mm.

      SIGMA_InVivo_Functional_Brain_csf.nii.gz
      SIGMA_InVivo_Functional_Brain_epi.nii.gz
      SIGMA_InVivo_Functional_Brain_gm.nii.gz
      SIGMA_InVivo_Functional_Brain_mask.nii.gz
      SIGMA_InVivo_Functional_Brain_t2.nii.gz
      SIGMA_InVivo_Functional_Brain_wm.nii.gz

  ### TSBTA sheep Brain Atlas Version 2.0 : Waxholm atlas Feat. SIGMA
  In this second version of the TSBTA resources we deliver a new TSBTA brain atlas obtained by the normalization of the Waxholm space published by Kleven, H. et al. Nat Methods (2023, https://doi.org/10.1038/s41592-023-02034-3).
  The Waxholm sheep brain atlas is currently the best numerical 3D atlas of the sheep brain.
  In accordance with authors of this paper we are authorized to modify and embed the WHS atlas within the TSBTA environement to standardize the identification of brain territories.
  We provide a normalized version the WHS for both ex-vivo and in-vivo of the anatomical TSBTA templates. Finally, we offer linear and non-linear transformations to enable your data to commute between the TSBTA and WHS ex-vivo environments using ANTs commands.
  
  #### Ex-vivo atlas
  WHS sheep brain atlas normalized in ex-vivo T2*-weighted TSBTA template + List of 222 labels created in ITKSnap Format + linear and non-linear transformations for SIGMA-WHS journeys (WHS-to-SIGMA_Transformations folder).

  Spatial resolution 0.09x0.09x0.09mm.

      SIGMA_ExVivo_Anatomical_Brain_Atlas.nii.gz
      SIGMA_ExVivo_Anatomical_Brain_Atlas.txt
      ./WHS-to-SIGMA_Transformations/reference_SIGMA.nii.gz
      ./WHS-to-SIGMA_Transformations/reference_WHS.nii.gz
      ./WHS-to-SIGMA_Transformations/WHS-in-SIGMA_transform_01_InverseWarp.nii.gz
      ./WHS-to-SIGMA_Transformations/WHS-in-SIGMA_transform_01_Warp.nii.gz
      ./WHS-to-SIGMA_Transformations/WHS-in-SIGMA_transform_02_GenericAffine.mat
      ./WHS-to-SIGMA_Transformations/WHS-in-SIGMA_transform_03_GenericAffine.mat
      ./WHS-to-SIGMA_Transformations/WHS_SD_rat_atlas_v4.nii.gz
      ./WHS-to-SIGMA_Transformations/WHS-to-SIGMA_byANTS.txt

  #### In-vivo atlas
WHS sheep brain atlas normalized in in-vivo T2 TSBTA anatomical template + List of 222 labels created in ITKSnap Format.

Spatial resolution 0.15x0.15x0.15mm.

      SIGMA_InVivo_Anatomical_Brain_Atlas.nii.gz
      SIGMA_InVivo_Anatomical_Brain_Atlas.txt

  #### TSBTA brain meshes
Rat brain mesh created using BrainNet viewers commands in matlab (https://www.nitrc.org/projects/bnv/).
  
  Spatial resolution 0.09x0.09x0.09mm.

      SIGMA_Anatomical_Brain_Atlas_mesh.nv

  #### TSBTA functional atlas
In the original publication of the TSBTA resources, we developed a functional atlas for the sheep brain, using a group ICA analysis validated through a RAICAR approach. From this analysis, we identified 59 bilateral ROIs covering cortical, sub-cortical and brainstem structures that are functionally distinct. Despite having been derived from purely functional data, this atlas broadly, if not precisely, correlates with the general anatomical boundaries and many are associated with specific anatomical structures. A primary motivation for the creation of this atlas is derived from the need to perform brain segmentations which is optimized for functional MRI analysis, since the signal sources do not necessarily match typical anatomical boundaries. A similar requirement has been identified by those performing human studies, resulting in efforts to generate more diverse, multi-modal atlases.

SIGMA sheep brain functional atlas normalized in in-vivo T2 TSBTA functional template + List of 59 labels created in ITKSnap Format.

  Spatial resolution 0.375x1x0.375mm.

      SIGMA_Functional_Brain_Atlas_Labels.txt
      SIGMA_Functional_Brain_Atlas_ListOfStructures.csv
      SIGMA_InVivo_Functional_Brain_Atlas.nii.gz

  #### TSBTA CT template
In this version of the TSBTA resources we included a CT/TEP template built from the data previously published (Barriere D.A. et al 2018 , Sci Rep. 2018 Jan 11;8(1):424. doi: 10.1038/s41598-017-18896-5) and acquired on a Triumph™ PET/CT dual modality imaging platform (Sherbrooke Univeristy, Québec, Canada. Gamma Medica, Inc., Northridge, CA, USA), acquired on a LabPET™ avalanche photodiode-based digital PET scanner with a 7.5 cm axial field-of-view capable of achieving an isotropic spatial resolution. A caudal injection of approximately 30 MBq of [18F]-FDG was applied followed by a static acquisition to evaluate [18F]-FDG uptake within brain. CT images were acquired from the high-resolution X-ray computed tomography (CT) modality. Images were reconstructed using the Triumph™ PET/CT software. [18F]-FDG images were reconstructed using 3-D MLEM algorithm providing images with a final resolution of 0.5 × 0.5 × 0.597 mm. CT scans were reconstructed using the standard FBP kernel analytical reconstruction algorithms, providing an isotropic image with a final resolution of 0.165 µm isotropic.
Both [18F]-FDG and CT data were spatially normalized to the TSBTA ex-vivo template using the previously described methods.

Spatial resolution 0.09x0.09x0.09mm.

      SIGMA_InVivo_18FDG_Brain_template.nii.gz
      SIGMA_InVivo_CT_Brain_template.nii.gz

## Important Note
SIGMA ressources are provided at the scanner resolution and are oriented in anterior commisure/posterior commisure axis. Center of the images have been set at the anterior commisure level (Bregma 0 mm). Nevertheless, users are invited to increase the resolution of the current images for using in SPM or FSL for accurate coregistration and normalization steps (we recommand x10 increasing). No manipulation of image resolution are required with ANTs. Not tested with AFNI.

For any questions regarding the TSBTA ressource, please email the TSBTA Team (sigma.preclinical.resources@gmail.com) or Email directly David A. Barrière (david.barriere@cnrs.fr).

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
