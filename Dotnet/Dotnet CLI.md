Dotnet Core CLI
======================

Commands
----------------------

Build for linux
```
dotnet build --runtime ubuntu.16.04-x64
```

Create a release build, targetting the latest dotnetcore
```
dotnet publish --configuration Release --framework netcoreapp2.2
```

Create a publish dir without rebuilding
```
dotnet publish --no-build
```
