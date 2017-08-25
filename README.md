# Analysis scripts for "The neural representation of personally familiar and unfamiliar faces in the distributed system for face perception"

This repository contains preprocessing and analysis scripts for "The neural representation of personally familiar and unfamiliar faces in the distributed system for face perception" by Matteo Visconti di Oleggio Castello, Yaroslav O. Halchenko, J. Swaroop
Guntupalli, Jason D. Gors, and M. Ida Gobbini. A preprint is available on [bioRxiv](http://biorxiv.org/content/early/2017/05/15/138297).

The dataset is available through [DataLad](http://datasets.datalad.org/?dir=/labs/gobbini/famface/data). Note that we have released data for one subject so far, and we'll release the entire dataset after publication.

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

### GLM

- [`group_multregress_openfmri.py`](group_multregress_openfmri.py):
  nipype pipeline to perform third (group) level univariate analysis
with FSL. Based on the pipeline provided by Satra Ghosh and Anne Park
(our thanks to them!)

### MVPC

- [`run_sl.py`](run_sl.py): main script to run searchlight analyses
- [`pymvpa2cosmo.py`](pymvpa2cosmo.py): script to convert PyMVPA
  datasets into CoSMoMVPA datasets for statistical testing using TFCE
- [`run_tfce_mvdoc_fx.m`](run_tfce_mvdoc_fx.m): script to run TFCE on
  accuracy maps using CoSMoMVPA
- [`ev_roi_clf.py`](ev_roi_clf.py): script to run additional decoding analyses in probabilistic masks of early visual areas
- [`permutation_testing_ev.Rmd`](permutation_testing_ev.Rmd): RMarkdown notebook that plots the results of the analysis in  probabilistic masks of early visual areas (see also pre-computed HTML output [`permutation_testing_ev.nb.html`](permutation_testing_ev.nb.html))
- [`hmax_familiarvsunfamiliar-id.Rmd`](hmax_familiarvsunfamiliar-id.Rmd): RMarkdown notebook used to analyze the decoding of images using HMAX features (see also pre-computed HTML output [`hmax_familiarvsunfamiliar-id.nb.html`](hmax_familiarvsunfamiliar-id.nb.html))

### Similarity of Representational Geometries

- [`notebooks/define_rois_mds.ipynb`](notebooks/define_rois_mds.ipynb):
  notebook used to obtain non-overlapping spherical ROIs in both the
task data and the movie hyperaligned data
- [`compute_dsmroi_firstlev.py`](compute_dsmroi_firstlev.py): script to
  compute first-level cross-validated representational dissimilarity matrices
- [`notebooks/compute_dsmroi_hpal.ipynb`](notebooks/compute_dsmroi_hpal.ipynb):
  notebook used to compute the similarity of representational geometries
using hyperaligned movie data
- [`notebooks/plot_mds.ipynb`](notebooks/plot_mds.ipynb):
  notebook used to generate MDS and circular graph plots for task and
hyperaligned data
- [`notebooks/get_between-within_correlations.ipynb`](notebooks/get_between-within_correlations.ipynb):
  notebook used to obtain dataframes with correlations between/within
systems for each subject (task data) or pair of subjects (hyperaligned
data)
- [`mds_betweenwithin_corr.Rmd`](mds_betweenwithin_corr.Rmd): RMarkdown
  notebook with additional analyses on correlations of RDMS
between/within systems (see rendering in
[`mds_betweenwithin_corr.nb.html`](mds_betweenwithin_corr.nb.html))


## Auxiliary and miscellaneous files

- [`mds_rois.py`](mds_rois.py): contains functions to run MDS analyses
- [`expdir.py`](expdir.py): to fetch directories used in analyses
- [`notebooks/scatterplots.ipynb`](notebooks/scatterplots.ipynb): notebook used to plot scatterplots shown in the supplementary material

