# Usa la imagen SDK de .NET 9.0 para compilar la aplicación
FROM mcr.microsoft.com/dotnet/sdk:9.0 AS build
WORKDIR /src

# Copia el archivo de proyecto y restaura dependencias
COPY *.csproj ./
RUN dotnet restore

# Copia el resto del código fuente y publica la aplicación
COPY . ./
RUN dotnet publish -c Release -o /app

# Usa la imagen de runtime de .NET 9.0 para ejecutar la aplicación
FROM mcr.microsoft.com/dotnet/aspnet:9.0 AS runtime
WORKDIR /app
COPY --from=build /app .

# Expone el puerto
EXPOSE 8080

# Reemplaza 'TuProyecto' con el nombre correcto de tu DLL
ENTRYPOINT ["dotnet", "dotnet.dll"]
