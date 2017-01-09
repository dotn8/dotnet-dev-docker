FROM microsoft/windowsservercore
SHELL ["powershell"]

RUN New-Item -ItemType Directory -Path "C:\\Resources"

RUN Invoke-WebRequest "https://download.microsoft.com/download/E/E/D/EEDF18A8-4AED-4CE0-BEBE-70A83094FC5A/BuildTools_Full.exe" -OutFile "C:\\Resources\\BuildTools_Full.exe" -UseBasicParsing
RUN & 'C:\\Resources\\BuildTools_Full.exe' /Silent /Full

RUN Invoke-WebRequest "https://download.microsoft.com/download/E/4/1/E4173890-A24A-4936-9FC9-AF930FE3FA40/NDP461-KB3102436-x86-x64-AllOS-ENU.exe" -OutFile "C:\\Resources\\NDP461-KB3102436-x86-x64-AllOS-ENU.exe" -UseBasicParsing
RUN & 'C:\\Resources\\NDP461-KB3102436-x86-x64-AllOS-ENU.exe' /features + /q

RUN Invoke-WebRequest "https://download.microsoft.com/download/8/2/F/82FF2034-83E6-4F93-900D-F88C7AD9F3EE/NDP46-TargetingPack-KB3045566.exe" -OutFile "C:\\Resources\\NDP46-TargetingPack-KB3045566.exe" -UseBasicParsing
RUN & C:\\Resources\\NDP46-TargetingPack-KB3045566.exe /features + /q

RUN New-Item -ItemType Directory -Path "C:\\bin"
ENV PATH="${PATH};C:\bin;C:\Program Files (x86)\MSBuild\14.0\Bin"
RUN Invoke-WebRequest "https://dist.nuget.org/win-x86-commandline/latest/nuget.exe" -OutFile "C:\\bin\\nuget.exe" -UseBasicParsing

CMD ["powershell"]
