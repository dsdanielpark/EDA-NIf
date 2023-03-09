# EDA-NIf (EDA NIfTI)
[![Contributor Covenant](https://img.shields.io/badge/contributor%20covenant-v2.0%20adopted-black.svg)](code_of_conduct.md)
[![Python Version](https://img.shields.io/badge/python-3.6%2C3.7%2C3.8-black.svg)](code_of_conduct.md)
![Pypi Version](https://img.shields.io/pypi/v/edanif.svg)
![Code convention](https://img.shields.io/badge/code%20convention-pep8-black)

Tool for *Exploratory Data Analysis of Neuroimaging Informatics Technology Initiative(NIfTI) format* <br>
`EDA-NIf` creates a dataframe containing meta information of NIfTi file format and provides several useful functions.
![](https://github.com/DSDanielPark/EDA-NIf/blob/main/tutorials/result/eda_nif.gif)
<br>


# Installation
  ```cmd
  pip install edanif
  ```
  Official documentation will be provided starting from major version 1.
<Br><Br>


# Tutorial
I will provide tutorial notebooks for all the features I made. I have a plan to write additional documentation with official release version (major version 1 or higher).

1. Main-tutorials: https://github.com/DSDanielPark/EDA-NIf/blob/main/tutorials/edanif_tutorial.ipynb
2. Sub-tutorial-folder: https://github.com/DSDanielPark/EDA-NIf/tree/main/tutorials

<br>


# Main Feature

  <details>
  <summary> See sample data folder tree... </summary>

The sample data folder is designed with an unnecessary and complex structure to show that all nifti files under the top-level folder path are collected recursively. If you are using the [BIDS format](https://bids.neuroimaging.io/), you only need to insert keywords properly.

Example folder tree
![](https://github.com/DSDanielPark/EDA-NIf/blob/main/tutorials/result/data_tree.png)
</details>

<br>

### `edanif.eda_nif.meta_df`
If you enter only the top-level folder containing nifti files, you can get a data frame for all nifti files.  <br>
1. In case of raw nifti files
    ```python
    import edanif

    df_raw_nii = edanif.meta_df('../data/raw_nifti', 'nii.gz', 'df_raw_nii_meta.csv', False)
    ```
    result dataframe: https://github.com/DSDanielPark/EDA-NIf/blob/main/tutorials/result/df_raw_nii_meta.csv

2. In case of mask nifti files (binary files `only`)
    ```python
    import edanif

    df_mask_nii = edanif.meta_df('../data/mask_nifti', 'mask.nii.gz', 'df_mask_nii_meta.csv', True)
    ```
    result dataframe: https://github.com/DSDanielPark/EDA-NIf/blob/main/tutorials/result/df_mask_nii_meta.csv

<br><br>

## Features

1. edanif.eda_nif <br>
  1.1 `count_center_voxel_labels` <br>
  1.2 `meta_df`: enter only the top-level folder containing nifti files, you can get a data frame for all nifti files. <br>

2. edanif.vis_nif <br>
  2.1 `save_nifti_images` <br>

3. edanif.utils.util <br>
  3.1 `find_all_files` <br>
  3.2 `save_print_instance`<br>

4. edanif.process.preprocess <br>
  4.1 `count_center_voxel_labels`<br>
  4.2 `if_minus_return_0`<br>
  4.3 `get_nonzero3d`<br>
  4.4 `get_nonzero3d_shape` <br>
  4.5 `get_hardcrop`<br>
  4.6 `threshold_at_two`<br>
  4.7 `monai_cropforeground`<br>
  4.8 `get_nonzero_xyz_of_nii`<br>

5. edanif.process.registration <br>
  5.1 `RegistrationMetric`<br>

6. edanif.process.resampling <br>
  6.1 `make_isotropic`<br>
  6.2 `resample_fixedsize_fixedspacing`<br>
  6.3 `resampling`<br>

7. edanif.process.trans_morph <br>
  7.1 `voxel_erosion`<br>
  7.2 `voxel_dilation`<br>
  7.3 `get_boundary_diff_index`<br>

- Feature development and unit testing are ongoing. We will update it whenever time permits.

<br><br>

# References
[1] NiBabel https://nipy.org/nibabel/ <br>
[2] SimpleITK https://simpleitk.org/ <br>
[3] MONAI https://monai.io/ <Br>
[4] AntsPy https://github.com/ANTsX/ANTsPy

<br>


### Contacts
Maintainer: [Daniel Park, South Korea](https://github.com/DSDanielPark) 
e-mail parkminwoo1991@gmail.com
