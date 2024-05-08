# Some instruction regarding the build process

It has been successfully built on python3.8 with later version of torch 2.2.0.

Note that the right cuda has to be loaded first, cuda 12.1.0 in this case.

Then mostly follow this link (https://github.com/MVIG-SJTU/AlphaPose/issues/1188)

export PATH=/usr/local/cuda/bin/:$PATH

export LD_LIBRARY_PATH=/usr/local/cuda/lib64/:$LD_LIBRARY_PATH

pip install -U pip setuptools

pip install cython==0.27.3

pip install easydict halpecocotools munkres natsort opencv-python pyyaml scipy tensorboardx terminaltables timm tqdm visdom jinja2 typeguard

python setup.py build develop

// Install PyTorch3D (Optional, only for visualization)

conda install -c fvcore -c iopath -c conda-forge fvcore iopath -y

conda install -c bottler nvidiacub -y

pip install pytorch3d

In the initial inference, there is also the cython_bbox issue due to numpy does not use float anymore after 1.20. The cython_bbox need to be updated and reinstalled
see issue (https://github.com/MVIG-SJTU/AlphaPose/issues/1148)
pip install git+https://github.com/valentin-fngr/cython_bbox.git 
