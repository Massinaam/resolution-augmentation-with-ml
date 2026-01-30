# Resolution augmentation with ML

This project explores using machine learning to reconstruct / enhance the resolution of imaging-like data (a super‑resolution style workflow) from multi-channel inputs. The work is provided as notebooks covering preprocessing, dataset preparation, and model implementation/training.

## Repository structure

- `Pre-Processing.ipynb` — preprocessing utilities (e.g., filtering/blur operations, handling HDF/H5 files).
- `BD.ipynb` — data preparation/exploration utilities (includes steps related to data access/download and general setup).
- `Network-Implementation.ipynb` — model definition (U-Net with residual blocks), dataset/dataloader creation, training loop and basic evaluation.
- `ML-Presentation-28_05.pptx` — project slides/presentation.

## Requirements

The notebooks were written to run in a Google Colab–style environment (with Google Drive mounting). If you run locally, you may need to adapt paths and dependencies.

Main dependencies (based on notebook imports):
- Python 3
- PyTorch
- NumPy, Pandas
- matplotlib
- h5py
- GDAL (`osgeo.gdal`) for reading some HDF data (can be tricky to install locally)
- tifffile (if you use the TIFF dataset parts)
- requests + BeautifulSoup4 (if you use the download/scraping cells)

> Note: GDAL is often easier to install via conda (e.g., `conda install -c conda-forge gdal`) than via pip.

## How to run

### Option A — Google Colab (recommended)
1. Open the notebooks in Colab.
2. Mount Google Drive when prompted.
3. Update paths (e.g., `content/drive/...`) to match your Drive folder structure.
4. Run notebooks in this order:
   1) `Pre-Processing.ipynb`
   2) `BD.ipynb`
   3) `Network-Implementation.ipynb`

### Option B — Local execution
1. Create and activate a virtual environment:
   ```bash
   python -m venv .venv
   source .venv/bin/activate
   pip install -U pip
