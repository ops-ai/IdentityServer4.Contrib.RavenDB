# IdentityServer 4 RavenDB stores

[![Quality Gate Status](https://sonarcloud.io/api/project_badges/measure?project=ops-ai_identityserver4-ravendb&metric=alert_status)](https://sonarcloud.io/dashboard?id=ops-ai_identityserver4-ravendb)
[![Build Status](https://opsai.visualstudio.com/BeyondAuth/_apis/build/status/ops-ai.IdentityServer4.Contrib.RavenDB?branchName=develop)](https://opsai.visualstudio.com/BeyondAuth/_build/latest?definitionId=4&branchName=develop)
[![Vulnerabilities](https://sonarcloud.io/api/project_badges/measure?project=ops-ai_identityserver4-ravendb&metric=vulnerabilities)](https://sonarcloud.io/dashboard?id=ops-ai_identityserver4-ravendb)
[![Coverage](https://sonarcloud.io/api/project_badges/measure?project=ops-ai_identityserver4-ravendb&metric=coverage)](https://sonarcloud.io/dashboard?id=ops-ai_identityserver4-ravendb)
![CodeQL](https://github.com/ops-ai/IdentityServer4.Contrib.RavenDB/workflows/CodeQL/badge.svg)

[![NuGet Status](https://img.shields.io/nuget/v/IdentityServer4.Contrib.RavenDB.svg?style=flat)](https://www.nuget.org/packages/IdentityServer4.Contrib.RavenDB/)
[![NuGet Count](https://img.shields.io/nuget/dt/IdentityServer4.Contrib.RavenDB.svg)](https://www.nuget.org/packages/IdentityServer4.Contrib.RavenDB/)

### Enable Document Expiration
```
await store.Maintenance.SendAsync(new ConfigureExpirationOperation(new ExpirationConfiguration
{
    Disabled = false,
    DeleteFrequencyInSec = 60
}));
```


### Register Claims and Principals custom IdentityServer serializers
```
documentStore.Conventions.CustomizeJsonSerializer += (JsonSerializer serializer) =>
{
    serializer.Converters.Add(new ClaimConverter());
    serializer.Converters.Add(new ClaimsPrincipalConverter());
};
```
