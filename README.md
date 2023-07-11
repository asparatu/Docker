# Docker
This library of Docker Compose yaml configuration file to run development environments on your pc.


### Port Error
Error invoking remote method 'docker-start-container': Error: (HTTP code 500) server error - Ports are not available: exposing port TCP 0.0.0.0:1433 -> 0.0.0.0:0: listen tcp 0.0.0.0:1433: bind: An attempt was made to access a socket in a way forbidden by its access permissions.

##### Solution
**PowerShell**
1. Disable Hyper-V: **dism.exe /Online /Disable-Feature:Microsoft-Hyper-V**
2. You need to reboot the computer or you will get when try run the command in number 3
3. Exclude Port: **netsh int ipv4 add excludedportrange protocol=tcp startport=(portnumber) numberofports=1**
...Repeat Command for other ports
4. Enable Hyper-V: **dism.exe /Online /Enable-Feature:Microsoft-Hyper-V /All**
5. Reboot computer for to take affect.