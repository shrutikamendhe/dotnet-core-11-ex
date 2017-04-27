FROM microsoft/dotnet:1.1-sdk

WORKDIR /app

EXPOSE 8080

COPY . .

RUN dotnet restore 

RUN dotnet publish

#ENTRYPOINT ["./.s2i/run"]

#ENTRYPOINT sleep 5000 | dotnet run -f netcoreapp1.1
ENTRYPOINT sleep 500000 | dotnet "/app/bin/Debug/netcoreapp1.1/dotnet-core-11-ex.dll"