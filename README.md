# nugeo-package-lock (created for https://github.com/NuGet/Home/issues/8103)
This projecct demonstrates the feature packages lock feature of Visual Studio 2017 15.9 & Nuget 5.0

Refer here : https://blog.nuget.org/20181217/Enable-repeatable-package-restores-using-a-lock-file.html

This repo has .Net 472 framework solution with one console application project. Console Application has packagage reference to [Honeywell.Testing.Package](https://www.nuget.org/packages/Honeywell.Testing.Package/).
The csproject has locked version of package with below settings

```xml
<ItemGroup>
    <PackageReference Include="Honeywell.Testing.Package" Version="0.1.0-*">      
    </PackageReference>
 </ItemGroup>
```

The nuget package manager has 3 pre-release versions of this packages 0.1.0-alpha0002,0.1.0-alpha0001,0.1.0-alpha0000. However, the console application
locked package version to 0.1.0-alpha0000.

You could use this repo to experiment witn /p:RestoreLockMode property switch with Visual Studio MSBuild to confirm the usage of lock file.

Make sure you have

1. VS 2017 15.9
2. NuGet 4.9
