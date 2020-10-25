# Joint.Docs.Swagger

## Docs

Adds API documentation using [Swagger](https://swagger.io/docs/).

## Installation

```
dotnet add package Joint.Docs.Swagger
```

## Dependencies

- [Joint](https://www.nuget.org/packages/Joint/)
- [Swashbuckle.AspNetCore.Swagger](https://www.nuget.org/packages/Swashbuckle.AspNetCore.Swagger/)
- [Swashbuckle.AspNetCore.SwaggerGen](https://www.nuget.org/packages/Swashbuckle.AspNetCore.SwaggerGen/)
- [Swashbuckle.AspNetCore.SwaggerUi](https://www.nuget.org/packages/Swashbuckle.AspNetCore.SwaggerUi/)

## Usage

Inside `Startup.cs` extend `IJointBuilder` with `AddSwaggerDocs()` and `IApplicationBuilder` with `UseSwaggerDocs()`:

```c#
public IServiceProvider ConfigureServices(this IServiceCollection services)
{
    var builder = JointBuilder
        .Create(services)
        .AddSwaggerDocs(Path.Combine(AppContext.BaseDirectory, $"{Assembly.GetExecutingAssembly().GetName().Name}.xml"));

    //other registrations
    return builder.Build();
}

public void Configure(this IApplicationBuilder app)
{
    app.UseSwaggerDocs();
}
```

Having this done your docs should be available at **http://{host}:{port}/{routePrefix}**

## Options

- Enabled - determines whether documentation is enabled
- Name - name of the documentation
- Title - title of the documentation
- Version - version of the documentation
- RoutePrefix - endpoint at which the documentation is going to be available
- IncludeSecurity - determines whether documentation security (via JWT) is going to be activated
- ContactName - name of person which we can contact
- ContactEmail - email of person which we can contact

### appsettings.json

```json
"swagger": {
    "enabled": true,
    "name": "v1",
    "title": "API",
    "version": "v1",
    "routePrefix": "docs",
    "includeSecurity": true,
    "contactName": "some-name",
    "contactEmail": "some.email@example.com"
  }
```

## Table of Contents

- [Joint](https://github.com/flapek/Joint)
- [Joint.Auth](https://github.com/flapek/Joint.Auth)
- [Joint.CQRS.Commands](https://github.com/flapek/Joint.CQRS.Commands)
- [Joint.CQRS.Events](https://github.com/flapek/Joint.CQRS.Events)
- [Joint.CQRS.Queries](https://github.com/flapek/Joint.CQRS.Queries)
- [Joint.DB.Mongo](https://github.com/flapek/Joint.DB.Mongo)
- [Joint.DB.Redis](https://github.com/flapek/Joint.DB.Redis)
- [Joint.Docs.Swagger](https://github.com/flapek/Joint.Docs.Swagger)
- [Joint.Exception](https://github.com/flapek/Joint.Exception)
- [Joint.Logging](https://github.com/flapek/Joint.Logging)
- [Joint.WebApi](https://github.com/flapek/Joint.WebApi)
