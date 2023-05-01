# SETUP STEPS

1. Open the project folder and run terminal with anaconda environment, create enviroment with name venv

```
Conda create -p venv python==3.8 -y 
```

2. create two files with names  setup.py and requirements.txt

```
#Sample Setup.py

from setuptools import setup, find_packages
from typing import List # To type hinting

def get_requirements(file_path:str)->List[str]:
    """
    input: None
    output: list of requirements
    Parse requirements from requirements.txt
    """
    requirements=[]
    with open(file_path) as f:
        requirements = f.readlines()
        requirements = [req.strip() for req in requirements]#list compreshension
        
    if "-e ." in requirements:
        requirements.remove("-e .")
    return requirements


setup(
name = "VAE Collaborative Filtering",
version = "0.0.1",
author="Alavi Khan",
author_email="leonasting@gmail.com",
packages = find_packages(),
install_requires = get_requirements('requirements.txt'),
description = "Variational Autoencoder for Collaborative Filtering",
)
```
