# Check .net package vulnerabilities

PowerShell commands (admin):

1. Run analyzer
> iex "& { $(irm https://aka.ms/install-artifacts-credprovider.ps1) }"
> dotnet nuget locals all --clear
> 
> dotnet restore --interactive
> 
> dotnet list package --include-transitive --vulnerable


2. Remove unused dep
> dotnet tool install --global NuGone --version 2.1.1
> 
> nugone analyze --project MySolution.sln


3. Package dependencies
> dotnet depends MySolution.sln
