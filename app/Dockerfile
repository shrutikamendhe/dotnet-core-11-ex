FROM microsoft/dotnet:1.1-sdk
COPY . /app
WORKDIR /app
 
RUN ["dotnet", "restore"]
RUN ["dotnet", "build"]
 
EXPOSE 8080/tcp
ENV ASPNETCORE_URLS http://*:8080
 
USER 0

#ENTRYPOINT ["dotnet", "run"]
ENTRYPOINT ["./.s2i/run"]

#FROM microsoft/dotnet:1.1-sdk
#
#WORKDIR /app
#
#EXPOSE 8080
#
#COPY . .
#
##RUN dotnet restore 
#
##RUN dotnet publish
##RUN dotnet publish -c Release -o out
#
##ENTRYPOINT ["./.s2i/run"]
#
##ENTRYPOINT sleep 5000 | dotnet run -f netcoreapp1.1
##ENTRYPOINT sleep 500000 | dotnet "/app/bin/Debug/netcoreapp1.1/dotnet-core-11-ex.dll"
#
##ENTRYPOINT ["dotnet", "out/dotnet-core-11-ex.dll"]
#
#
#RUN ["dotnet", "restore"]
#RUN ["dotnet", "build"]
#
#ENTRYPOINT ["dotnet", "run"]