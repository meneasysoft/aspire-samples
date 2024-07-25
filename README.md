#Individual

![alt text](image.png)
![alt text](image-1.png)

Das Dashboard von Aspire war zunächst nicht aufrufbar - Protokol musste in Code Spaces von HTTP auf HTTPS umgestellt werden:
![alt text](image-2.png)

Dann ist Aspire-Dashboard ladbar über Link in Debugging-Console:
![alt text](image-3.png)

Bei Zertifikatsfehlern (Code Spaces Github) - folgende Befehle im Terminal auf dem Codespace ausführen:
dotnet tool update -g linux-dev-certs
dotnet linux-dev-certs install
siehe: https://learn.microsoft.com/de-de/aspnet/core/security/enforcing-ssl?view=aspnetcore-8.0&tabs=visual-studio%2Clinux-ubuntu#trust-the-aspnet-core-https-development-certificate-on-windows-and-macos

Auch interessant: https://github.com/dotnet/aspire/issues/2914


WeatherApp auf spezifischem Port
https://github.com/dotnet/aspire/discussions/3702

var weatherApi = builder.AddProject<Projects.AspireJavaScript_MinimalApi>("weatherapi")
    .WithHttpEndpoint(name: "weatherapi", port: 9999, isProxied: false)
    .WithExternalHttpEndpoints();

Sieht so aus
![alt text](image-4.png)
https://??.app.github.dev/weatherforecast
Portprotokoll in Github Codespace Port Bereich: http

Swagger für WetterAPI
https://??.app.github.dev/swagger/index.html
![alt text](image-5.png)

@meneasysoft ➜ .../aspire-samples/samples/AspireWithJavaScript/AspireJavaScript.Vue (main) $ npm run build

https://??.app.github.dev/

Vue:
https://??.app.github.dev/main.js

Minimal-API-Swagger

https://??.app.github.dev/swagger/index.html


AppHost
dotnet workload restore [/workspaces/aspire-samples/samples/AspireWithJavaScript/AspireJavaScript.AppHost/AspireJavaScript.AppHost.csproj]

Via Code Space Console

dotnet run --project samples/AspireWithJavaScript/AspireJavaScript.MinimalApi/AspireJavaScript.MinimalApi.csproj 

URL
https://??.app.github.dev/weatherforecast

# .NET Aspire Samples

[![CI (main)](https://github.com/dotnet/aspire-samples/actions/workflows/ci.yml/badge.svg)](https://github.com/dotnet/aspire-samples/actions/workflows/ci.yml)

Samples for .NET Aspire.

[.NET Aspire](https://aka.ms/aspireannouncement) is a stack for building resilient, observable, cloud-native apps with .NET.

## Official Samples

Official samples hosted in this repo can be accessed via the [Samples browser](https://learn.microsoft.com/samples/browse/?expanded=dotnet&products=dotnet-aspire).

Sample highlights include:

- [Aspire Shop](./samples/AspireShop/)
- [Metrics with OpenTelemetry, Prometheus & Grafana](./samples/Metrics)
- [Integrating a Node.js app](./samples/AspireWithNode)
- [Integrating DAPR](./samples/AspireWithDapr)
- [Persisting data in composed containers using volume mounts](./samples/VolumeMount)
- [Working with database containers](./samples/DatabaseContainers)
- [Integrating clients apps like WinForms](./samples/ClientAppsIntegration)

## eShop

[eShop](https://github.com/dotnet/eshop) is a reference .NET application implementing an eCommerce web site using a services-based architecture using .NET Aspire.

## .NET Aspire Links

- [.NET Aspire Documentation](https://learn.microsoft.com/dotnet/aspire)
- [.NET Aspire Blog](https://aka.ms/aspireannouncement)
- [.NET Aspire GitHub](https://github.com/dotnet/aspire)

## License

.NET (including the aspire-samples repo) is licensed under the [MIT license](./LICENSE).

## Disclaimer

The sample applications provided in this repository are intended to illustrate individual concepts that may be beneficial in understanding the underlying technology and its potential uses. These samples may not illustrate best practices for production environments.

The code is not intended for operational deployment. Users should exercise caution and not rely on the samples as a foundation for any commercial or production use. See [ASP.NET Core security topics](https://learn.microsoft.com/aspnet/core/security/) for more information on security concerns related to hosting ASP.NET Core applications.

## Contributing

We welcome contributions to this repository of samples related to official .NET Aspire hosting and components pieces (i.e. those pieces who's code lives in the [Aspire repo](https://github.com/dotnet/aspire) and that ship from the [**Aspire** NuGet account](https://www.nuget.org/profiles/aspire)). It's generally a good idea to [log an issue](https://github.com/dotnet/aspire-samples/issues/new/choose) first to discuss any idea for a sample with the team before sending a pull request.

## Code of conduct

This project has adopted the code of conduct defined by the [Contributor Covenant](https://contributor-covenant.org) to clarify expected behavior in our community. For more information, see the [.NET Foundation Code of Conduct](https://www.dotnetfoundation.org/code-of-conduct).
