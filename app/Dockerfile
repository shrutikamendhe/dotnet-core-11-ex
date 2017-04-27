FROM microsoft/dotnet:1.1-sdk
EXPOSE 8080

ENV DOTNET_CORE_VERSION=1.1

ENV LANG=C.UTF-8 \
    HOME=/opt/app-root \
    PATH=/opt/app-root/src/.local/bin:/opt/app-root/src/bin:/opt/app-root/bin:/opt/app-root/node_modules/.bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin \
    DOTNET_PUBLISH_PATH=/opt/app-root/publish 

RUN mkdir -p /opt/app-root/src /opt/app-root/publish && \
    useradd -u 1001 -r -g 0 -d /opt/app-root/src -s /sbin/nologin \
      -c "Default Application User" default && \
    chown -R 1001:0 /opt/app-root

WORKDIR /opt/app-root/src

USER 1001

COPY . .

ENV ASPNETCORE_URLS=http://*:8080

RUN ["dotnet", "restore"]

RUN chmod +x ./s2i/run

ENTRYPOINT sleep 500000 | ./s2i/run

#FROM microsoft/dotnet:1.1-sdk
#COPY . /app
#WORKDIR /app
 #
#RUN ["dotnet", "restore"]
#RUN ["dotnet", "build"]
 #
#EXPOSE 8080/tcp
#ENV ASPNETCORE_URLS http://*:8080
 #
#USER 0
#
##ENTRYPOINT ["dotnet", "run"]
##ENTRYPOINT ["./.s2i/run"]
#ENTRYPOINT sleep 50000 | ./.s2i/run

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