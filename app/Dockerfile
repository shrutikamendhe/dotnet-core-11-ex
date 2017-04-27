FROM microsoft/dotnet:1.1-sdk

WORKDIR /app

EXPOSE 8080

COPY . .

RUN dotnet restore

ENTRYPOINT ["sleep", "500000000"]