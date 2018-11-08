FROM microsoft/dotnet:2.1-aspnetcore-runtime AS base
WORKDIR /app
EXPOSE 80

FROM microsoft/dotnet:2.1-sdk AS build
WORKDIR /src
COPY ["Core.Service.Sample/Core.Service.Sample.csproj", "Core.Service.Sample/"]
RUN dotnet restore "Core.Service.Sample/Core.Service.Sample.csproj"
COPY . .
WORKDIR "/src/Core.Service.Sample"
RUN dotnet build "Core.Service.Sample.csproj" -c Release -o /app

FROM build AS publish
RUN dotnet publish "Core.Service.Sample.csproj" -c Release -o /app

FROM base AS final
WORKDIR /app
COPY --from=publish /app .
ENTRYPOINT ["dotnet", "Core.Service.Sample.dll"]