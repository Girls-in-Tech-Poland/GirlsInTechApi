# GirlsInTechApi

Contains a starter .NET Core 3.1 to demonstrate App Service deployment

## (Try this at home)
It's totally possible to build your ASP.NET Core application locally and push it out to the app service

- Navigate to `GirlsInTechApi` folder containing the `GirlsInTechApi.csproj` project file
- Execute the following commands to build your API locally
  ```bash
  dotnet restore
  dotnet build --configuration Release --no-restore
  dotnet publish --configuration Release --no-build
  ```

- The contents of the published app will be emitted into:
`GirlsInTechApi\GirlsInTechApi\bin\Release\netcoreapp3.1\publish\`
- At this point the result of `dotnet publish` need to be packaged into a `.zip` file using your preferred method
  - If you don't have a preference, we recommend using [7-zip](https://www.7-zip.org/)
- The application can be deployed using:
```bash
az webapp deployment source config-zip --src <path-to-zip-file> --name <app-service-name> --resource-group <resource-group>
```