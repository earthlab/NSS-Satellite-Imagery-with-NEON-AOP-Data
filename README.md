<!-- [![Join the chat at https://gitter.im/earthlab/NSS-Satellite-Imagery-with-NEON-AOP-Data](https://badges.gitter.im/earthlab/NSS-Satellite-Imagery-with-NEON-AOP-Data.svg)](https://gitter.im/earthlab/NSS-Satellite-Imagery-with-NEON-AOP-Data?utm_source=badge&utm_medium=badge&utm_campaign=pr-badge&utm_content=badge) -->

# NSS-Satellite-Imagery-with-NEON-AOP-Data

This repository holds iPython notebooks which process NEON imaging spectrometer (NIS) data to spectrally and spatially align with satellite image datasets from Landsat 8 and Sentinel 2. 

The `spectral_response_cutoff` folder holds json files which contain weights and band indexes for the NIS data to be resampled to a satellite's larger bandwidth multispectral band. It can be loaded directly into a Python dictionary object using:

```
import json
with open('NIS_weights_L8.json') as fi:
    nis_weights = json.load(fi)

# get the Near-Infrared weights for the Landsat 8 NIR band
nir_weights, nir_bands = nis_weights['L8_NIR']

# construct a single NIR band using those weights and band indexes, stored in simul_l8_nir
# nis_hs_cube is of shape [bands, rows, cols]
simul_l8_nir = nis_hs_cube[nir_bands] * nir_weights / nir_weights.sum()

```


Clone the repository
```
git clone https://github.com/earthlab/NSS-Satellite-Imagery-with-NEON-AOP-Data
```


<!-- Tuesday AM - Fill out a form for access to [Planet Education and Research Account](https://forms.gle/qWhabjrKKNY6w8tH8). If you go through the standard process it may not be approved in time for the afternoon session. -->

<!-- Tuesday PM - Hands On with Planet and NEON data. -->

<!-- Clone this repository - there are example .ipynb notebooks for you to work with during the breakout sessions -->


