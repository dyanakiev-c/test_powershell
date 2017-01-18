# Remote application Installation

How perform a basic installation on a remote windows machine.
Two local VMs were used to perform the testing:
_1 running Windows Server_
_1 running CentOS_

The windows machine has a SSH server configured as described on [this link](https://winscp.net/eng/docs/guide_windows_openssh_server)


## Windows machine has the following ps script
Installation of file
```ps
$pathvarg = {C:\Users\Administrator\Folder\file.exe /S /v/qn }
Invoke-Comand -ScriptBlock $pathvarg

```
The machine needs to have remote script execution enabled:
```ps
Set-ExecutionPolicy RemoteSigned
```

## Establish connection to the windows machine
Connect using Administrator username and password

```
ssh Administrator@192.168.56.102
```
Navigate to the script location and execute the following:

```ps
powershell -command .\install.ps1
```

## To check the final result

Open the windows machine explorer and navigate to the directory
C:\Program Files (x86)\Notepad++

## To Do

1. Take the .exe location as a input parameter rather than have it hard coded.
2. Add a Return message for the result of the execution
..* Success or fail
3. Make an unistall version
