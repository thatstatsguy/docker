Source 1: https://www.youtube.com/watch?v=Qg022XIzQKY
At the time writing, docker desktop is not supported on Windows Server - we need to go a different route to getting the docker engine on the machine

In windows server
1. Open Windows PowerShell (Admin)
2. Excecute ```Install-Module DockerMsftProvider -Force``` (Answer Y to any prompts)
3. Execute ```Install-Package -Name docker -Provider DockerMsftProvider``` (Answer Y to any prompts)
4. Reboot server
5. To confirm that it's install, On server mananger dashboard -> add roles and features. Click next until you get to features and you should see Containers (installed)
6. Reopen Powershell
7. Execute ```Get-WindowsFeature -Name containers```
8. You can pull the windows nano-server with ```docker image pull mcr.microsoft.com/windows/nanoserver:1809```

Source 2:
Doesn't mention anything about pulling, supposed to be natively supported out the box with windows server
https://github.com/docker/labs/blob/master/windows/windows-containers/README.md