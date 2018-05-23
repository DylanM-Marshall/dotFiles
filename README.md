# dotFiles
O2 commands, etc

## Deep learning APIs - Keras / Tensorflow

1) **instantiate interactive session: **
(calling 4 cours, 128 Gigs RAM, maximum time (11 hours, 59 minutes), gpu queue, 2 gpus)
> `srun -n 4 --pty --mem 128G -t 11:59:00 -p gpu --gres=gpu:2 /bin/bash`
2) **load necessary modules: **
(gcc, cuda, cuda specific python 2.7)
> `module load gcc/4.8.5 cuda/8.0 python/2.7.12-ucs4`
3) **create or load virtual environment: **
(only need to create once, source from that point onwards)
> `virtualenv GPUpython27` # create
> `source GPUpython27/bin/activate` # load
4) **install libraries: **
(look at the INSTALL.txt file in this repository to confirm libraries, NOTE: tensorflow-gpu==1.4.0, NOT any more recent versions, is the one you want - trust me...)
> `pip install -r INSTALL.txt`

## Jupyter notebook / lab set up:

1) instantiating an interactive session 
  - examples on O2 confluence and the o2 bashrc text file in this Github repository
  - **IMPORTANT AS HECK -->** add the `export XDG_RUNTIME_DIR=""` to the end of your `.bash_profile` file on o2
2) loading necessary modules 
  - examples found throughout the functions in the o2 bashrc text file
    - `module load gcc/6.2.0 python/3.6.0`
3) creating or loading a virtual environment, good idea to have it located in your /home/{your username} directory
  - CREATING... 
    - `python[3.6] -m venv {your virtualenv}`
  - LOADING... 
    - `source {your virtualenv}/bin/activate`
  - note that python3.6 is tricky on O2, this is because O2's default python is python2.7. Therefore if whatever it is that you're doing is python3.6, python3.6 needs to be prepended in your command
    - e.g: `python3.6 ...`
4) Installing external PyPi modules such as pyBigWig, Tensorflow, Keras, Numpy. The `pip` command installs directly to the virtual-environment which you are presumably in at this point.
  - `pip install ...`
  - once again, if you're using Python3.6, it is different:
    - `pip3.6 install ...`
