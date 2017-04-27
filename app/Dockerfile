FROM microsoft/dotnet:1.1-sdk

WORKDIR /app

EXPOSE 8080

COPY . .

RUN dotnet restore

#ENTRYPOINT ["./.s2i/run"]

#ENTRYPOINT sleep 5000 | dotnet run -f netcoreapp1.1
ENTRYPOINT sleep 500000 | ./.s2i/run