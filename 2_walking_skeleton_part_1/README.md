
# Create the basic functionality of the project

## Setup the project directory

```s
> mkdir DatingApp
> cd DatingApp
```

## Check installation status

```s
> dotnet --info 
.NET SDK (reflecting any global.json):
 Version:   5.0.202     
 Commit:    db7cc87d51  

Runtime Environment:    
 OS Name:     Windows   
 OS Version:  10.0.19042
 OS Platform: Windows   
 RID:         win10-x64
 Base Path:   C:\Program Files\dotnet\sdk\5.0.202\

Host (useful for support):
  Version: 5.0.5
  Commit:  2f740adc14

.NET SDKs installed:
  5.0.202 [C:\Program Files\dotnet\sdk]

.NET runtimes installed:
  Microsoft.AspNetCore.App 5.0.5 [C:\Program Files\dotnet\shared\Microsoft.AspNetCore.App]        
  Microsoft.NETCore.App 5.0.5 [C:\Program Files\dotnet\shared\Microsoft.NETCore.App]
  Microsoft.WindowsDesktop.App 5.0.5 [C:\Program Files\dotnet\shared\Microsoft.WindowsDesktop.App]

To install additional .NET runtimes or SDKs:
  https://aka.ms/dotnet-download
```

## Check .NET Help

```s
> dotnet -h
.NET SDK (5.0.202)
Usage: dotnet [runtime-options] [path-to-application] [arguments]

Execute a .NET application.

runtime-options:
  --additionalprobingpath <path>   Path containing probing policy and assemblies to probe for.
  --additional-deps <path>         Path to additional deps.json file.
  --depsfile                       Path to <application>.deps.json file.
  --fx-version <version>           Version of the installed Shared Framework to use to run the application.
  --roll-forward <setting>         Roll forward to framework version  (LatestPatch, Minor, LatestMinor, Major, LatestMajor, Disable).
  --runtimeconfig                  Path to <application>.runtimeconfig.json file.

path-to-application:
  The path to an application .dll file to execute.

Usage: dotnet [sdk-options] [command] [command-options] [arguments]

Execute a .NET SDK command.

sdk-options:
  -d|--diagnostics  Enable diagnostic output.
  -h|--help         Show command line help.
  --info            Display .NET information.
  --list-runtimes   Display the installed runtimes.
  --list-sdks       Display the installed SDKs.
  --version         Display .NET SDK version in use.

SDK commands:
  add               Add a package or reference to a .NET project.
  build             Build a .NET project.
  build-server      Interact with servers started by a build.
  clean             Clean build outputs of a .NET project.
  help              Show command line help.
  list              List project references of a .NET project.
  msbuild           Run Microsoft Build Engine (MSBuild) commands.
  new               Create a new .NET project or file.
  nuget             Provides additional NuGet commands.
  pack              Create a NuGet package.
  publish           Publish a .NET project for deployment.
  remove            Remove a package or reference from a .NET project.
  restore           Restore dependencies specified in a .NET project.
  run               Build and run a .NET project output.
  sln               Modify Visual Studio solution files.
  store             Store the specified assemblies in the runtime package store.
  test              Run unit tests using the test runner specified in a .NET project.
  tool              Install or manage tools that extend the .NET experience.
  vstest            Run Microsoft Test Engine (VSTest) commands.

Additional commands from bundled tools:
  dev-certs         Create and manage development certificates.
  fsi               Start F# Interactive / execute F# scripts.
  sql-cache         SQL Server cache command-line tools.
  user-secrets      Manage development user secrets.
  watch             Start a file watcher that runs a command when files change.

Run 'dotnet [command] --help' for more information on a command.
```

## Investigate the `new` command

```s
> dotnet new -h
Usage: new [options]

Options:
  -h, --help          Displays help for this command.
  -l, --list          Lists templates containing the specified template name. If no name is specified, lists all templates.
  -n, --name          The name for the output being created. If no name is specified, the name of the output directory is used.
  -o, --output        Location to place the generated output.
  -i, --install       Installs a source or a template pack.
  -u, --uninstall     Uninstalls a source or a template pack.
  --interactive       Allows the internal dotnet restore command to stop and wait for user input or action (for example to complete authentication).
  --nuget-source      Specifies a NuGet source to use during install.
  --type              Filters templates based on available types. Predefined values are "project" and "item".
  --dry-run           Displays a summary of what would happen if the given command line were run if it would result in a template creation.
  --force             Forces content to be generated even if it would change existing files.
  -lang, --language   Filters templates based on language and specifies the language of the template to create.
  --update-check      Check the currently installed template packs for updates.
  --update-apply      Check the currently installed template packs for update, and install the updates.
```

## Create a new solution file

```s
> dotnet new sln
The template "Solution File" was created successfully.
> ls


    Directory: C:\repos\udemy-dotnet-angular\DatingApp


Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
-a----         6/27/2021   6:09 PM            550 DatingApp.sln

```

## Create a new API

```s
> dotnet new webapi -o API
The template "ASP.NET Core Web API" was created successfully.

Processing post-creation actions...
Running 'dotnet restore' on API\API.csproj...
  Determining projects to restore...
C:\repos\udemy-dotnet-angular\DatingApp\API\API.csproj : error NU1100: Unable to resolve 'Swashbuckle.AspNetCore (>= 5.6.3)' for 'net5.0'.
  Failed to restore C:\repos\udemy-dotnet-angular\DatingApp\API\API.csproj (in 99 ms).
Restore failed.
Post action failed.
Description: Restore NuGet packages required by this project.
Manual instructions: Run 'dotnet restore'

PS C:\repos\udemy-dotnet-angular\DatingApp> dotnet restore
  Determining projects to restore...
C:\Program Files\dotnet\sdk\5.0.202\NuGet.targets(131,5): warning : Unable to find a project to restore! [C:\repos\udemy-dotnet-angular\DatingApp\DatingApp.sln]
```

## Add API into solution

```s
> dotnet sln add API
Project `API\API.csproj` added to the solution.
```