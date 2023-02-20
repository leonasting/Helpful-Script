# Environemnt File Export

1. Exporting environment details using pip.
```
pip freeze > requirements.txt
```

2. Recreating environment using the requirements file.
```
# using pip
pip install -r requirements.txt

# using Conda
conda create --name <env_name> --file requirements.txt
```
