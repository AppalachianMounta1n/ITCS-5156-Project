# ITCS-5156-Project
Repository for my final project for ITCS 5156 at UNC Charlotte.

## Errors and Fixes
- When running ``pip install -r requirements.txt`` for installing the project dependencies for the original code, an error occurs in which ``sklearn`` has been deprecated in the current stable release of Python3 and must be removed from the file. Since the replacement, ``scikit-learn``, is already in the ``requirements.txt`` file, this can be fixed by simply removing ``sklearn`` from the file.
- When running ``pip install -r requirements.txt`` for installing the project dependencies for the original code, a notification error shows that no version of any package was found matching the requirement ``psnr-hvm`` despite the package displaying on [PyPi](https://pypi.org/project/psnr-hvsm/). I suspect this is due to the specific package name ``psnr-hvm`` being incorrect, as the package I located is actually called ``psnr-hvsm``, which solves the error.
- Each package will be given version specification requirements based on which package versions work and future encountered errors.
- The instructions for utilizing datasets stated that the videos must be placed within the ``datasets/train`` and ``datasets/inference`` folders, for training and testing respectively, but this folder does not exist. In order to fix this issue, I created said folder for usage.

## Source Links
### Original Code
- [Goluck Konuko Repo](https://github.com/Goluck-Konuko/animation-based-codecs)

### Datasets
- [Original Project Datasets](https://drive.google.com/drive/folders/1g0U1ZCTszm3yrmIewg7FahXsxyMBfxKj)
- [Additional Datasets]()

### Checkpoints
- [Original Project Checkpoints](https://drive.google.com/drive/folders/1_jIt9Bg-o_1-8_11DkVuHBvqHQH5e4tS)
- [My Checkpoints]()