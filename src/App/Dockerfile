FROM mcr.microsoft.com/dotnet/sdk:5.0 AS build
COPY . ./App
WORKDIR /App
RUN dotnet build -c Release -o output

FROM mcr.microsoft.com/dotnet/runtime:5.0 as runtime

COPY --from=build /App/output App/
WORKDIR /App
ENTRYPOINT ["dotnet", "Nyami.Hello.Docker.dll"]