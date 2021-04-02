FROM mcr.microsoft.com/dotnet/sdk:5.0 AS build
WORKDIR /app
COPY /dotnet5-api-in-kubernetes.csproj .
RUN dotnet restore dotnet5-api-in-kubernetes.csproj
COPY . .
RUN dotnet build dotnet5-api-in-kubernetes.csproj -c Release -o /out
FROM mcr.microsoft.com/dotnet/aspnet:5.0 AS runtime
WORKDIR /app
COPY --from=build /out ./
ENTRYPOINT ["dotnet", "dotnet5-api-in-kubernetes.dll"]