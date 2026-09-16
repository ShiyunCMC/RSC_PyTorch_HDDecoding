# RSC PyTorch HD decoding

This is a small learning project that ports the first step of your MATLAB RSC head-direction decoding workflow into Python and PyTorch.

The starting notebook is:

- `notebooks/01_mlp_hd_decoder.ipynb`
- `notebooks/01a_mlp_hd_decoder_L1L2regularization.ipynb` is the same first decoder, but uses explicit L1 + L2 regularization in the training loss instead of AdamW weight decay.

It follows the same broad data logic as `ind_window_cyldOnly_rev_progression.m`:

1. Load one `sessionData.mat` file and the matching CNMF-E `.hdf5` file.
2. Keep accepted calcium components.
3. Clip negative calcium values and min-max normalize during open field.
4. Select one cylinder window: pre-rotation, post-rotation, or dark.
5. Train a simple MLP decoder from population activity to `[cos(HD), sin(HD)]`.
6. Recover decoded HD with `atan2`.
7. Plot actual versus decoded HD and circular error.

The first notebook intentionally leaves out the MATLAB pipeline's shuffle tests, lag search, Bayesian posterior model, and split-cell analyses. Those are good next modules after the PyTorch basics feel comfortable.

## Setup

In VS Code, create/select a Python environment and install:

```bash
pip install -r requirements.txt
```

If `sessionData.mat` is MATLAB v7.3, `h5py` is used. If you later want a friendlier reader for complicated MATLAB cells/structs, install `mat73` too:

```bash
pip install mat73
```
