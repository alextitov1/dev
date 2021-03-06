# dotnet cli

## list install versions
```console
dotnet --list-sdks
dotnet --list-runtimes
```

## add project to existing solution

```sh
dotnet new console --use-program-main --output newProjectDir --framework net6.0 // create a new project
dotnet sln OtusLABs.sln add stack/stack.csproj // add a project to the solution
```

```sh
dotnet new sln
dotnet new console --output folder1/folder2/myapp
dotnet new console --framework net5.0
```

```
// add project to a solution
dotnet sln add folder1/folder2/myapp


dotnet sln todo.sln list


dotnet new sln -n mysolution
dotnet new console -o myapp
dotnet new classlib -o mylib1
dotnet new classlib -o mylib2
dotnet sln mysolution.sln add myapp\myapp.csproj
dotnet sln mysolution.sln add mylib1\mylib1.csproj --solution-folder mylibs
dotnet sln mysolution.sln add mylib2\mylib2.csproj --solution-folder mylibs


dotnet sln todo.sln remove **/*.csproj
```

dotnet run

