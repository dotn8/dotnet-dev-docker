FROM nloum/msbuild:4.6
SHELL ["powershell"]

RUN Invoke-WebRequest "https://download.microsoft.com/download/8/A/F/8AFFDD5A-53D9-46EB-98D7-B61BBCAF0DE6/vstf_testagent.exe" -OutFile "C:\\Resources\\vstf_testagent.exe" -UseBasicParsing
RUN & C:\\Resources\\vstf_testagent.exe /Full /Q

CMD ["powershell"]
