FROM mcr.microsoft.com/dotnet/sdk:5.0 AS build
WORKDIR /source

COPY ConversaoPeso.Web.csproj .
RUN dotnet restore

COPY . .
RUN dotnet publish -c release -o /app --no-restore

FROM mcr.microsoft.com/dotnet/aspnet:5.0
WORKDIR /app
COPY --from=build /app ./
ENTRYPOINT ["dotnet", "ConversaoPeso.Web.dll"]