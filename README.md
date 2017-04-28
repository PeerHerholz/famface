# TITLE

This repository contains preprocessing and analysis scripts for "..." by
Matteo Visconti di Oleggio Castello, Yaroslav O. Halchenko, J. Swaroop
Guntupalli, Jason D. Gors, and M. Ida Gobbini.

## Preprocessing and GLM modeling

- [`fmri_ants_openfmri.py`](fmri_ants_openfmri.py): nipype pipeline to
  perform preprocessing (spatial normalization to MNI 2 mm using ANTs,
first and second level univariate analysis using FSL). Based on the
example with the same name from stock Nipype
- [`pymvpa_hrf.py`](pyvmpa_hrf.py): script to run a GLM using PyMVPA and
  Nipy, to extract betas used for multivariate analysis
- [`make_unionmask.py`](make_unionmask.py): script to make a union mask
- [`stack_betas.py`](stack_betas.py): script to stack betas for
  multivariate analysis

## Analysis

- [`group_multregress_openfmri.py`](group_multregress_openfmri.py):
  nipype pipeline to perform third (group) level univariate analysis
with FSL. Based on the pipeline provided by Satra Ghosh and Anne Park
(our thanks to them!)
- [`run_sl.py`](run_sl.py): main script to run searchlight analyses
- [`pymvpa2cosmo.py`](pymvpa2cosmo.py): script to convert PyMVPA
  datasets into CoSMoMVPA datasets for statistical testing using TFCE
- [`run_tfce_mvdoc_fx.m`](run_tfce_mvdoc_fx.m): script to run TFCE on
  accuracy maps using CoSMoMVPA
- [`compute_dsmroi_firstlev.py`](compute_dsmroi_firstlev.py): script to
  compute first-level cross-validated representational dissimilarity matrices
- [`notebooks/define_rois_mds.ipynb`](notebooks/define_rois_mds.ipynb):
  notebook used to obtain non-overlapping spherical ROIs in both the
task data and the movie hyperaligned data
- [`notebooks/compute_dsmroi_hpal.ipynb`](notebooks/compute_dsmroi_hpal.ipynb):
  notebook used to generate first level RDMs using hyperaligned movie
data
- [`notebooks/plot_mds.ipynb`](notebooks/plot_mds.ipynb):
  notebook used to generate MDS and circular graph plots for task and
hyperaligned data


## Auxiliary modules

- [`mds_rois.py`](mds_rois.py): contains functions to run MDS analyses
- [`expdir.py`](expdir.py): to fetch directories used in analyses

