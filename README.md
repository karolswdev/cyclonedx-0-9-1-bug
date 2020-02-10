# dotnet CycloneDX 0.9.1 bug

## Required setup

* Clone this repository
* Install dotnet-CycloneDX 0.9.1
* Run CycloneDX and see the error

## Install CycloneDX 0.9.1

```bash
dotnet tool install --global CycloneDX --version 0.9.1
```
## Run CycloneDX 0.9.1

Ensure you are in the *CycloneDX* folder. Execute the following

```bash
dotnet CycloneDX CycloneDX.sln -o bom.xml
```

You should see the following error:
```
Retrieving Dependent.Project 1.0.0
Unhandled exception. System.ArgumentNullException: Value cannot be null. (Parameter 'stream')
   at NuGet.Packaging.Core.NuspecCoreReaderBase..ctor(Stream stream, Boolean leaveStreamOpen)
   at NuGet.Packaging.NuspecReader..ctor(Stream stream, IFrameworkNameProvider frameworkProvider, Boolean leaveStreamOpen)
   at NuGet.Packaging.NuspecReader..ctor(Stream stream)
   at CycloneDX.Services.NugetService.GetComponentAsync(String name, String version) in /Users/steve/Development/CycloneDX/cyclonedx-dotnet/CycloneDX/Services/NugetService.cs:line 109
   at CycloneDX.Services.NugetService.GetComponentAsync(NugetPackage package) in /Users/steve/Development/CycloneDX/cyclonedx-dotnet/CycloneDX/Services/NugetService.cs:line 186
   at CycloneDX.Program.OnExecuteAsync() in /Users/steve/Development/CycloneDX/cyclonedx-dotnet/CycloneDX/Program.cs:line 158
   at McMaster.Extensions.CommandLineUtils.Conventions.ExecuteMethodConvention.InvokeAsync(MethodInfo method, Object instance, Object[] arguments)
   at McMaster.Extensions.CommandLineUtils.Conventions.ExecuteMethodConvention.OnExecute(ConventionContext context, CancellationToken cancellationToken)
   at McMaster.Extensions.CommandLineUtils.Conventions.ExecuteMethodConvention.<>c__DisplayClass0_0.<<Apply>b__0>d.MoveNext()
--- End of stack trace from previous location where exception was thrown ---
   at McMaster.Extensions.CommandLineUtils.CommandLineApplication.ExecuteAsync(String[] args, CancellationToken cancellationToken)
   at McMaster.Extensions.CommandLineUtils.CommandLineApplication.ExecuteAsync[TApp](CommandLineContext context, CancellationToken cancellationToken)
   at CycloneDX.Program.Main(String[] args) in /Users/steve/Development/CycloneDX/cyclonedx-dotnet/CycloneDX/Program.cs:line 62
   at CycloneDX.Program.<Main>(String[] args)
```