# escape=`
ARG WindowsTag=ltsc2022
FROM mcr.microsoft.com/windows/servercore:${WindowsTag}

WORKDIR C:/
SHELL ["powershell", "-Command", "$ErrorActionPreference = 'Stop'; $ProgressPreference = 'SilentlyContinue';"]
RUN Set-ExecutionPolicy Bypass -Scope Process -Force; Invoke-Expression ((New-Object System.Net.WebClient).DownloadString('https://community.chocolatey.org/install.ps1'))
RUN choco install -y 7zip
RUN Invoke-WebRequest 'http://repo.msys2.org/distrib/msys2-x86_64-latest.tar.xz' -OutFile 'msys2-x86_64-latest.tar.xz'; 7z x msys2-x86_64-latest.tar.xz; rm msys2-x86_64-latest.tar.xz; 7z x msys2-x86_64-latest.tar; rm msys2-x86_64-latest.tar
ENV PATH="C:/msys64/opt/bin;C:/msys64/mingw64/bin;C:/msys64/usr/bin;C:/msys64/bin;C:/Windows/system32;C:/Windows;C:/Windows/System32/Wbem;C:/Windows/System32/WindowsPowerShell/v1.0/;C:/Windows/System32/OpenSSH/;C:/Users/ContainerAdministrator/AppData/Local/Microsoft/WindowsApps" `
    MSYSTEM=MINGW64 `
    TERM=xterm-256color `
    Bash="C:/msys64/usr/bin/bash.exe"


SHELL ["C:\\msys64\\usr\\bin\\bash.exe", "-lc"]
RUN exit
RUN ["C:\\msys64\\usr\\bin\\pacman.exe","-Syyuu","--noconfirm","--ask=20","--noprogressbar"]
RUN ["C:\\msys64\\usr\\bin\\pacman.exe","-Su","--noconfirm","--ask=20","--noprogressbar"]
RUN ["C:\\msys64\\usr\\bin\\pacman.exe","-Scc","--noconfirm","--ask=20","--noprogressbar"]
ENTRYPOINT [ "C:/msys64/usr/bin/bash.exe","-l" ]
