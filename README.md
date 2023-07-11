# Docker
This library of Docker Compose yaml configuration file to run development environments on your pc.


#### Port Error
Error invoking remote method 'docker-start-container': Error: (HTTP code 500) server error - Ports are not available: exposing port TCP 0.0.0.0:1433 -> 0.0.0.0:0: listen tcp 0.0.0.0:1433: bind: An attempt was made to access a socket in a way forbidden by its access permissions.

#### Solution
##### **PowerShell**
1. Disable Hyper-V
    ```
    dism.exe /Online /Disable-Feature:Microsoft-Hyper-V
    ````
2. Reboot the computer
3. Exclude Ports
    ```
    netsh int ipv4 add excludedportrange protocol=tcp startport=(portnumber) numberofports=1
    ```
4. Enable Hyper-V
   ```
   dism.exe /Online /Enable-Feature:Microsoft-Hyper-V /All
    ```
5. Reboot the computer to take affect