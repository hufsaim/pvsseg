# pvsseg
Automatic perivascular space segmentation on T2-weighted MR images

![pvs](pvsseg.png)

## Frangi filtering
- Frangi filtering can effectively highlight the perivascular spaces in the white matter. 
- However, since many false positives occur at the tissue interfaces, a predefined ROI mask and additional FP reduction step are often required.
- [Frangi filtering (jupyter notebook)](notebook/example_frangi_T2.ipynb)

## Frangi-based BG PVS volume calculation in the neonatal brain
- Input: 3D T2-weigthed MR image & Tissue segmentation from [infant freesurfer](https://github.com/hufsaim/pvsseg)
- Output: BG (Basal Ganglia) PVS segmentation
![BG PVS segmentation of neonatal brain](https://github.com/hufsaim/pvsseg/blob/main/notebook/neonate_bgpvs_vol.png)
- [BG PVS volume calculation (jupyter notebook)](notebook/neonate_bgpvs_vol.ipynb)

## DL-based ROI & PVS segmentation
- A deep learning is an effective way to reduce false positives.
- In our initial method, the DL model was designed in a way that classfies FP from the Frangi filtering result [(HBM 2021)](https://doi.org/10.1002/hbm.25194). 
  - [Inference code](#pvsseg)
- The new version was learned using the PVS and ROI segmentations, both ROI (white matter & deep gray matter regions) and PVS can be simultaneously segmented from T2 input.
  - [Inference code](#pvsseg)
