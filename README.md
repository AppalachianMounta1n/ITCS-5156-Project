# ITCS-5156-Project
Repository for my final project for ITCS 5156 at UNC Charlotte. This repository is a recreation of [https://github.com/Goluck-Konuko/animation-based-codecs](https://github.com/Goluck-Konuko/animation-based-codecs) and contains the source code for the following papers: [ULTRA-LOW BITRATE VIDEO CONFERENCING USING DEEP IMAGE ANIMATION](https://arxiv.org/abs/2012.00346v1),
[A HYBRID DEEP ANIMATION CODEC FOR LOW-BITRATE VIDEO CONFERENCING](https://arxiv.org/abs/2207.13530) and 
[PREDICTIVE CODING FOR ANIMATION-BASED VIDEO COMPRESSION](https://arxiv.org/abs/2307.04187)

## Errors and Fixes
- When running ``pip install -r requirements.txt`` for installing the project dependencies for the original code, an error occurs in which ``sklearn`` has been deprecated in the current stable release of Python3 and must be removed from the file. Since the replacement, ``scikit-learn``, is already in the ``requirements.txt`` file, this can be fixed by simply removing ``sklearn`` from the file.
- When running ``pip install -r requirements.txt`` for installing the project dependencies for the original code, a notification error shows that no version of any package was found matching the requirement ``psnr-hvm`` despite the package displaying on [PyPi](https://pypi.org/project/psnr-hvsm/). I suspect this is due to the specific package name ``psnr-hvm`` being incorrect, as the package I located is actually called ``psnr-hvsm``, which solves the error.
- Each package will be given version specification requirements based on which package versions work and future encountered errors.
- The instructions for utilizing datasets stated that the videos must be placed within the ``datasets/train`` and ``datasets/inference`` folders, for training and testing respectively, but this folder does not exist. In order to fix this issue, I created said folder for usage.
- Python3 uses the ``python3`` command instead of the ``python`` command to run files, so I had to modify each of their scripts that used this command or the ``python`` environment rather than the ``python3`` environment to fix this.
- When attempting to run the training script, the ``urllib3`` and ``chardet`` versions did not match a supported version. Additionally, the ``facenet_pytorch`` module was not found, which may be related. By adding ``facenet-pytorch==2.5.3`` to the ``requirements.txt`` file, I was able to fix the ``facenet-pytorch`` error. Debugging and fixing the errors with ``urllib3`` and ``chardet`` is ongoing, with determinations in progress for the specific versions needed. PyTorch is also not installed due to unknown problems, so this is being diagnosed.
- A file not found error occurs if the videos are in an improperly named folder. The folder path on my machine that worked was ``/home/$USER/Documents/datasets/``, with the folders of video data then immediately within this folder. The ``train_cat`` folder of the provided datasets must be renamed to ``hevc_40`` as well. The supported and functional file structure will be added in a later version of this README.md.
- Some of the video files within the ``hevc_46`` dataset have improper names and must be renamed to fit the expected names of the provided scripts. This is extremely tedious.

## Necessary File Structure For Replication
- To begin, I believe it necessary to state that it seems as if the original creator hard-coded which datasets and filenames would be used for *any* training or functionality, so I will have to rewrite this if I wish to use additional datasets.
- When run, the training script will search for a folder called ``datasets`` within the same directory as the code. Within this folder, the following folders with data must be placed: ``hevc_38``, ``hevc_40``, ``hevc_42``, ``hevc_46``, and ``hevc_50``. The file names within cannot be changed yet.
- The original datasets are provided as ``hevc_38.tar.gz``, ``hevc_42.tar.gz``, ``hevc_46.tar.gz``, ``hevc_50.tar.gz``, and these will contain folders to be renamed. ``train`` and ``inference`` are the folders that will hold the training data and testing data respectively. ``hevc_50.tar.gz`` will decompress to ``train_hevc``, which must be renamed to ``hevc_50``. ``hevc_38.tar.gz`` and ``hevc_46.tar.gz`` will decompress to  ``out`` which must be renamed to 

## Training The Model
- To train the model, run the ``script_training.sh {model}`` Bash script from the source code. {model} should be equal to one of the models with a YAML file in the ``config`` folder. The supported options are ``dac``, ``hdac``, and ``rdac``.

## Source Links
### Original Code
- [Goluck Konuko Repo](https://github.com/Goluck-Konuko/animation-based-codecs)

### Datasets
- The [Original Project Datasets](https://drive.google.com/drive/folders/1g0U1ZCTszm3yrmIewg7FahXsxyMBfxKj) are ``VoxCeleb``, ``TalkingHead-1KH``, and ``CREMA-D``, which are used for the inference datasets. Additional videos are provided for training purposes based on conventional codecs.
- [Additional Datasets]()

### Checkpoints
- [Original Project Checkpoints](https://drive.google.com/drive/folders/1_jIt9Bg-o_1-8_11DkVuHBvqHQH5e4tS)
- [My Checkpoints]()