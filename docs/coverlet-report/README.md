# Coverlet - generate code coverage report

Steps to generate:
- install tool:
> dotnet tool install -g dotnet-reportgenerator-globaltool                                                                                                   

- generate coverage.cobertura.xml:
> dotnet test --collect:"XPlat Code Coverage" --logger "console;verbosity=normal"

- generate html
> reportgenerator "-reports:Tests\Grid.Api.Tests\TestResults\*\coverage.cobertura.xml" "-targetdir:Tests\Grid.Api.Tests\TestResults\report" -reporttypes:Html


## Links
- [github - Coverlet - Cross platform code coverage for .NET](https://github.com/coverlet-coverage/coverlet)
