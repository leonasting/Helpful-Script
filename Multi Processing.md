1. Nohup
To run things in background and disconnect from the main terminal window.
```
nohup command &
eg:-nohup mpirun -np 18  python custom_train3.py 2>&1 | tee pick2.out &
```
2. On windows laptop
```
 mpiexec.exe -n 1 python .\train.py
```
