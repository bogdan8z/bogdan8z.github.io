# Coverlet - generate code coverage report

Steps to generate:
1. install tool:
> dotnet tool install -g dotnet-reportgenerator-globaltool                                                                                                   

2. generate coverage.cobertura.xml:
> dotnet test --collect:"XPlat Code Coverage" --logger "console;verbosity=normal"

3. generate html
> reportgenerator "-reports:Tests\Grid.Api.Tests\TestResults\*\coverage.cobertura.xml" "-targetdir:Tests\Grid.Api.Tests\TestResults\report" -reporttypes:Html


## Links
- [github - Coverlet - Cross platform code coverage for .NET](https://github.com/coverlet-coverage/coverlet)
