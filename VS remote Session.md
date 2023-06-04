# Visual Studio Code Remote Developement throgh SSH

**Does not work with HPC as if vs server application is not installed on the serve**

## General Steps

1. Get the following extension. The extensions tab can be accessed by shortcut(Ctrl+Shift+X [windows])
  1. Remote - SSH
  2. Python (Optional)
  3. Jupyter(Optional)
2. Click on the bottom left button "Open the remote window"
3. If you are aware of command to access the remote server type it in the dialog box and follow along.
```bash
example:
ssh 168982709@coe-hpc1.sjsu.edu 
ssh student@xyx.xyb.xyx.xyx
ssh -p 2020 student@xyx.xyb.xyx.xyx
```


## Setup
VS Studion Can connect to only linux servers

1. Check if your connect via SSH present in yout operating system.//client

```
optional: -p [portnumber]
ssh -p [port number] user@host
exampel ssh -p 2222 atos@192.168.0.106
exampel ssh -p 2222 168982709@coe-hpc1.sjsu.edu 


```
2. Check if your server has git installed by command ``` git ```.//server
3. Check installation of vscode.//client
4. Check extention remote development.//
5. Create New Window. Click bottom left button of remote connection-> click:connect current window to host-> Type host address 
```
Example 
Optional [:Port Number]
SSH 019848287@coe-hpc1.sjsu.edu[:Port Number] -A
```
6. Select save location . First is for specific user Program data location is general for all users.
7. Click Connect.


