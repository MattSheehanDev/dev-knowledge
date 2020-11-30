Dotnet
======================

Setup
-----------------------------------------

Install SDK
```
brew cask install dotnet-sdk
```

The Dotnet versioning can seem a little weird sometimes.
- There is the release version which usually matches the Runtime version, and then there is the SDK version which usually has a different version than the release and certain SDK's are versioned based off of what version of Visual Studio they are for.
- If you are not using Visual Studio, use the latest SDK version.


Dotnet CLI
------------------------------------------------

Create a new sln file
```
dotnet new sln -n <solution-name>
```

Create a new console project dir
```
dotnet new console -n <project-name>
```

Add a project to a sln file
```
dotnet sln <solution-file.sln> add <project-path.csproj>
```

Remove a project from a sln file
```
dotnet sln <solution-file.sln> remove <project-path.csproj>
```

