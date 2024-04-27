# Anaconda memory issue

Source: [Stack Overflow](https://stackoverflow.com/questions/65263972/anaconda-folder-is-taking-too-much-space)  

## Commands
1. Removes Tarball of installed packages
```
conda clear -all
```
2. Remove index cache, lock files, unused cache packages, and tarballs.
```
conda clean -all
```
3.Package removal
```
conda remove -n myenv scipy
conda remove scipy
```

4. Environement Removal
```
conda remove --envname
```
