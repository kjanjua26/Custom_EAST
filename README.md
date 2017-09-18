# Custom_EAST
EAST paper implementation repository modified for custom detection tasks. 

This is an implementation of research paper: https://arxiv.org/abs/1704.03155v2
The code was, actually, written by ArgMan, check out his repository: https://github.com/argman/EAST

This version is modified implementation of EAST to include the calculation of fps on images i.e. the fps on cpu and gpu will also be calculated. 

# Dependencies
Following dependencies are required to run this. 

1. Install Anaconda package from https://docs.anaconda.com/anaconda/install/ for python3. 
2. Create a conda environment `conda create -n tensorflow3 python=3.5`.
3. Install tensorflow v1.3 `pip3 install tensorflow`.

# Working

1. To use this, clone or zip download the repository. 
2. Give input dataset path and output directory in the `eval.py` file. 
3. The results, coordinates of boxes and boxes on the detected text in images, will be in your output directory. 

# Running on CPU

1. To run this on CPU, just type `python3 eval.py |tee out`. Use `|tee out` to store output in out file for viewing. 

# Running on GPU

1. To run this on GPU, you need to install and then add CUDA's path in `~/.bashrc` file in.
   Add these lines to  `.bashrc` file: 
   
   `export PATH=/usr/local/cuda/bin:${PATH}
    export MANPATH=/usr/local/cuda/man:${MANPATH}
    if [[ "${LD_LIBRARY_PATH}" != "" ]]
    then
      export LD_LIBRARY_PATH=/usr/local/cuda/lib64:${LD_LIBRARY_PATH}
    else
      export LD_LIBRARY_PATH=/usr/local/cuda/lib64
    fi
    `
2. Specify the GPU in `eval.py` file.
3. Type:
        1. `source ~/.bashrc\n`
        2. `export CUDA_VISIBLE_DEVICES=GPU_Number\n`
        3. `python3 eval.py |tee out`
        
