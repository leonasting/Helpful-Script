# 1. Creating the environment
## a.Create a directory
```
mkdir environments
```

## b. creating an environment inside the directory
```
cd environments
python3 -m venv NAMENEV
NAMENEV\Scripts\activate.bat # ON WINDOWS
source NAMENEV/bin/activate # ON LINUX/MAC
```
# 2. Creating the environment using conda at the base
```
conda create --name envname python=3.9
```

# 3. Creating the environment using conda at the separate path
```
conda create -p venv/ python=3.9
```
