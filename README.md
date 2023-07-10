# Docker
This library of Docker Compose yaml configuration file to run development environments on your pc.


### Port Error
Error invoking remote method 'docker-start-container': Error: (HTTP code 500) server error - Ports are not available: exposing port TCP 0.0.0.0:1433 -> 0.0.0.0:0: listen tcp 0.0.0.0:1433: bind: An attempt was made to access a socket in a way forbidden by its access permissions.

* Solution
1. Open CMD as Administrator
2. net stop winnat
3. docker start container_name or docker compose
4. net start winnat

* Exclude from Hyper-V using PowerShell
1. Disable Hyper-V: dism.exe /Online /Disable-Feature:Microsoft-Hyper-V
2. Exclude Port: netsh int ipv4 add excludedportrange protocol=tcp startport=(portnumber) numberofports=1
3. Enable Hyper-V: dism.exe /Online /Enable-Feature:Microsoft-Hyper-V /All