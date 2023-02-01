# snyk-repro

```
cd C:\Code\snyk-repro\SnykRepro\Proj2\obj

npx snyk monitor --org=greg-test --detection-depth=999


Monitoring C:\Code\snyk-repro\SnykRepro\Proj2\obj (obj)...

Explore this snapshot at https://app.snyk.io/org/greg-test/project/aaca73b7-d9d0-4bd8-a10c-8b469b46fc4a/history/bd00c239-c533-4e10-a8b5-81175794a57c

Notifications about newly disclosed issues related to these dependencies will be emailed to you.
```

Notice that:
- Proj1 has `<PackageReference Include="Autofac" Version="6.4.0" />`
- Proj2 has `<ProjectReference Include="..\Proj1\Proj1.csproj" />` and `<PackageReference Include="Serilog" Version="2.12.0" />`
- the `Proj2/obj/project.assets.json` file lists both `Autofac` and `Serilog`
- only `Serilog` is listed as a dependency in Snyk

Note that `project.assets.json` contains all of this info: https://github.com/Greg-Smulko/snyk-repro/blob/main/SnykRepro/Proj2/obj/project.assets.json includes Autofac.
