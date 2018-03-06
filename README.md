# dotFiles
o2 commands, etc

### o2 set up workflow

Installing software on a compute cluster is always tricky, O2 is no exception. For Python, installation and loading of software modules requires the following steps to be followed exactly otherwise things get messy:

1) instantiating an interactive session 
  - examples on O2 confluence and the o2 bashrc text file in this Github repository
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

Good Luck! 
