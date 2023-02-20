# Environemnt File Export

1. Exporting environment details.
```
pip freeze > requirements.txt

conda list --export > requirements.txt
```

2. Recreating environment using the requirements file.
```
# using pip
pip install -r requirements.txt

# using Conda
conda create --name <env_name> --file requirements.txt
```
