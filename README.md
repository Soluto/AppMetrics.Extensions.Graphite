# App Metrics Graphite Extensions

[![Official Site](https://img.shields.io/badge/site-appmetrics-blue.svg)](https://alhardy.github.io/app-metrics-docs/getting-started/intro.html) [![License](https://img.shields.io/badge/License-Apache%202.0-blue.svg)](https://opensource.org/licenses/Apache-2.0) [![Coverage Status](https://coveralls.io/repos/github/alhardy/AppMetrics.Extensions.Graphite/badge.svg?branch=master)](https://coveralls.io/github/alhardy/AppMetrics.Extensions.Graphite?branch=master)

|AppVeyor|Travis|
|:--------:|:--------:|
|[![Build status](https://ci.appveyor.com/api/projects/status/w2l7xmxlvyxy3988?svg=true)](https://ci.appveyor.com/project/alhardy/appmetrics-extensions-graphite/branch/master)|[![Build status](https://travis-ci.org/alhardy/AppMetrics.Extensions.Graphite.svg?branch=master)](https://travis-ci.org/alhardy/AppMetrics.Extensions.Graphite?branch=master)|

|Package|Dev Release|Pre-Release|Release|
|------|:--------:|:--------:|:--------:|
|App.Metrics.Extensions.Reporting.Graphite|[![MyGet Status](https://img.shields.io/myget/alhardy/v/App.Metrics.Extensions.Reporting.Graphite.svg)](https://www.myget.org/feed/alhardy/package/nuget/App.Metrics.Extensions.Reporting.Graphite)|[![NuGet Status](https://img.shields.io/nuget/vpre/App.Metrics.Extensions.Reporting.Graphite.svg)](https://www.nuget.org/packages/App.Metrics.Extensions.Reporting.Graphite/)|[![NuGet Status](https://img.shields.io/nuget/v/App.Metrics.Extensions.Reporting.Graphite.svg)](https://www.nuget.org/packages/App.Metrics.Extensions.Reporting.Graphite/)

## What is it?

The repo contains Graphite extension packages to [App Metrics](https://github.com/alhardy/AppMetrics).

#### Grafana/Graphite Web Monitoring

![Grafana/Graphite Generic Web Dashboard Demo](#todo) *TODO*

> Grab the dashboard [here](##todo) *TODO*

#### Grafana/Graphite OAuth2 Client Monitoring on a Web API

![Grafana/Graphite Generic OAuth2 Web Dashboard Demo](#todo) *TODO*

> Grab the dashboard [here](#todo) *TODO*

### Grafana/Graphite Web Application Setup

*TODO*

## How to build

[AppVeyor](https://ci.appveyor.com/project/alhardy/appmetrics-extensions-graphite/branch/master) and [Travis CI](https://travis-ci.org/alhardy/AppMetrics.Extensions.Graphite) builds are triggered on commits and PRs to `dev` and `master` branches.

See the following for build arguments and running locally.

|Configuration|Description|Default|Environment|Required|
|------|--------|:--------:|:--------:|:--------:|
|BuildConfiguration|The configuration to run the build, **Debug** or **Release** |*Release*|All|Optional|
|PreReleaseSuffix|The pre-release suffix for versioning nuget package artifacts e.g. `beta`|*ci*|All|Optional|
|CoverWith|**DotCover** or **OpenCover** to calculate and report code coverage, **None** to skip. When not **None**, a coverage file and html report will be generated at `./artifacts/coverage`|*OpenCover*|Windows Only|Optional|
|SkipCodeInspect|**false** to run ReSharper code inspect and report results, **true** to skip. When **true**, the code inspection html report and xml output will be generated at `./artifacts/resharper-reports`|*false*|Windows Only|Optional|
|BuildNumber|The build number to use for pre-release versions|*0*|All|Optional|


### Windows

Run `build.ps1` from the repositories root directory.

```
	.\build.ps1'
```

**With Arguments**

```
	.\build.ps1 --ScriptArgs '-BuildConfiguration=Release -PreReleaseSuffix=beta -CoverWith=OpenCover -SkipCodeInspect=false -BuildNumber=1'
```

### Linux & OSX

Run `build.sh` from the repositories root directory. Code Coverage reports are now supported on Linux and OSX, it will be skipped running in these environments.

```
	.\build.sh'
```

**With Arguments**

```
	.\build.sh --ScriptArgs '-BuildConfiguration=Release -PreReleaseSuffix=beta -BuildNumber=1'
```

> #### Nuget Packages
> Nuget packages won't be generated on non-windows environments by default.
> 
> Unfortunately there is [currently no way out-of-the-box to conditionally build & pack a project by framework](https://github.com/dotnet/roslyn-project-system/issues/1586#issuecomment-280978851). Because `App.Metrics` packages target `.NET 4.5.2` as well as `dotnet standard` there is a work around in the build script to force `dotnet standard` on build but no work around for packaging on non-windows environments. 

## Contributing

See the [contribution guidlines](https://github.com/alhardy/AppMetrics/blob/master/CONTRIBUTING.md) in the [main repo](https://github.com/alhardy/AppMetrics) for details.

## Acknowledgements

* [DocFX](https://dotnet.github.io/docfx/)
* [Fluent Assertions](http://www.fluentassertions.com/)
* [XUnit](https://xunit.github.io/)
* [StyleCopAnalyzers](https://github.com/DotNetAnalyzers/StyleCopAnalyzers)
* [Cake](https://github.com/cake-build/cake)
* [OpenCover](https://github.com/OpenCover/opencover)

***Thanks for providing free open source licensing***

* [Jetbrains](https://www.jetbrains.com/dotnet/) 
* [AppVeyor](https://www.appveyor.com/)
* [Travis CI](https://travis-ci.org/)
* [Coveralls](https://coveralls.io/)

## License

This library is release under Apache 2.0 License ( see LICENSE ) Copyright (c) 2016 Allan Hardy
