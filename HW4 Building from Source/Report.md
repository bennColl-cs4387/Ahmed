
## Build Process for YouTubeExplode

### Project: [YouTubeExplode](https://github.com/Tyrrrz/YoutubeExplode)

#### Build Process:
To begin, I forked the repository and cloned it locally using `git clone`. I ensured that the .NET SDK was installed, following the instructions on the [.NET SDK download page](https://dotnet.microsoft.com/download).
Thank god for Microsoft as .NET is backward compatible and it deosn't matter what version is running. For reference I am running version (v8.0.401) LTS
Once set up, I navigated to the project folder and ran the build command using `dotnet build`, which successfully compiled the project.

No errors during the process. 

After the build, I attempted to run the tests included in the repository by using `dotnet test`, but I noticed that the documentation didn't clearly explain how to run or interpret the test results.

#### What Went Well:
The overall build process was straightforward. There was no need for any additional setup or complex configurations.

#### What Went Poorly:
The major area where I encountered issues was in running the tests. While the project includes tests, there is no direct explanation or instructions in the documentation on how to execute them. Furthermore, no details were provided on what should be expected after the tests are run (e.g., success criteria, test output). I had to rely on general .NET knowledge to run `dotnet test` and understand the results.

Another minor issue was the lack of a clear explanation for first-time users on how to install the .NET SDK. While experienced developers might find this intuitive, newcomers may struggle without explicit instructions, me included.

#### Suggestions for Improving Build Documentation:
I don't think there should be any changes that will have a big difference other than making the git beginner-friendly. The Project does need it's own Contributing file as the READ ME is becoming very long. Here are some minor changes I am proposing. 
1. **Adding a section on running tests**: It would be helpful to include a dedicated section on how to run the tests, especially for developers who are new to the .NET ecosystem. A few lines in the README or a separate `CONTRIBUTING.md` file explaining how to execute `dotnet test` and interpret the results would improve the onboarding experience for new developers.
   
2. **Adding details on the project's structure**: Including a brief explanation of the project's folder structure (e.g., what each folder contains) would help new contributors navigate the codebase more efficiently. This would reduce the learning curve, this project is small and this might not make sense but projects get big out of nowhere so it is better to do it now when things are small. 

#### Updated Documentation Suggestion:
Here's a sample update to the project's README:

```markdown
## Prerequisites
Before building the project, you need to have the [.NET SDK](https://dotnet.microsoft.com/download) installed. Ensure that you're using the required version by running:
```bash
dotnet --version
```

## Building the Project
To build the project, simply run:
```bash
dotnet build
```

## Running Tests
To run the included tests, use the following command:
```bash
dotnet test
```
This will execute all the tests and display the results in the terminal. Ensure that all tests pass before submitting changes.

---

#### Fork Link:
[My Fork of YouTubeExplode](https://github.com/ahmed-esh/YoutubeExplode)



```
➜  git cd YoutubeExplode 
➜  YoutubeExplode git:(master) dotnet --version

8.0.402
➜  YoutubeExplode git:(master) dotnet build


Welcome to .NET 8.0!
---------------------
SDK Version: 8.0.402

Telemetry
---------
The .NET tools collect usage data in order to help us improve your experience. It is collected by Microsoft and shared with the community. You can opt-out of telemetry by setting the DOTNET_CLI_TELEMETRY_OPTOUT environment variable to '1' or 'true' using your favorite shell.

Read more about .NET CLI Tools telemetry: https://aka.ms/dotnet-cli-telemetry

----------------
Installed an ASP.NET Core HTTPS development certificate.
To trust the certificate, run 'dotnet dev-certs https --trust'
Learn about HTTPS: https://aka.ms/dotnet-https

----------------
Write your first app: https://aka.ms/dotnet-hello-world
Find out what's new: https://aka.ms/dotnet-whats-new
Explore documentation: https://aka.ms/dotnet-docs
Report issues and find source on GitHub: https://github.com/dotnet/core
Use 'dotnet --help' to see available commands or visit: https://aka.ms/dotnet-cli
--------------------------------------------------------------------------------------
An issue was encountered verifying workloads. For more information, run "dotnet workload update".
  Determining projects to restore...
  Restored /Users/temp/git/YoutubeExplode/YoutubeExplode.Demo.Cli/YoutubeExplode.Demo.Cli.csproj (in 17.45 sec).
  Restored /Users/temp/git/YoutubeExplode/YoutubeExplode.Converter.Tests/YoutubeExplode.Converter.Tests.csproj (in 32.48 sec).
  Restored /Users/temp/git/YoutubeExplode/YoutubeExplode.Tests/YoutubeExplode.Tests.csproj (in 32.53 sec).
  Restored /Users/temp/git/YoutubeExplode/YoutubeExplode/YoutubeExplode.csproj (in 34.47 sec).
  Restored /Users/temp/git/YoutubeExplode/YoutubeExplode.Converter/YoutubeExplode.Converter.csproj (in 34.47 sec).
  Restored /Users/temp/git/YoutubeExplode/YoutubeExplode.Demo.Gui/YoutubeExplode.Demo.Gui.csproj (in 47.48 sec).
  YoutubeExplode -> /Users/temp/git/YoutubeExplode/YoutubeExplode/bin/Debug/netstandard2.0/YoutubeExplode.dll
  YoutubeExplode -> /Users/temp/git/YoutubeExplode/YoutubeExplode/bin/Debug/net461/YoutubeExplode.dll
  YoutubeExplode -> /Users/temp/git/YoutubeExplode/YoutubeExplode/bin/Debug/netcoreapp3.1/YoutubeExplode.dll
  YoutubeExplode -> /Users/temp/git/YoutubeExplode/YoutubeExplode/bin/Debug/netstandard2.1/YoutubeExplode.dll
  YoutubeExplode -> /Users/temp/git/YoutubeExplode/YoutubeExplode/bin/Debug/net8.0/YoutubeExplode.dll
  YoutubeExplode.Converter -> /Users/temp/git/YoutubeExplode/YoutubeExplode.Converter/bin/Debug/net8.0/YoutubeExplode.Converter.dll
  YoutubeExplode.Demo.Cli -> /Users/temp/git/YoutubeExplode/YoutubeExplode.Demo.Cli/bin/Debug/net8.0/YoutubeExplode.Demo.Cli.dll
  YoutubeExplode.Converter -> /Users/temp/git/YoutubeExplode/YoutubeExplode.Converter/bin/Debug/netstandard2.0/YoutubeExplode.Converter.dll
  YoutubeExplode.Converter -> /Users/temp/git/YoutubeExplode/YoutubeExplode.Converter/bin/Debug/netstandard2.1/YoutubeExplode.Converter.dll
  YoutubeExplode.Converter -> /Users/temp/git/YoutubeExplode/YoutubeExplode.Converter/bin/Debug/netcoreapp3.1/YoutubeExplode.Converter.dll
  YoutubeExplode.Tests -> /Users/temp/git/YoutubeExplode/YoutubeExplode.Tests/bin/Debug/net8.0/YoutubeExplode.Tests.dll
  YoutubeExplode.Converter -> /Users/temp/git/YoutubeExplode/YoutubeExplode.Converter/bin/Debug/net461/YoutubeExplode.Converter.dll
  YoutubeExplode.Converter.Tests -> /Users/temp/git/YoutubeExplode/YoutubeExplode.Converter.Tests/bin/Debug/net8.0/YoutubeExplode.Converter.Tests.dll
  YoutubeExplode.Demo.Gui -> /Users/temp/git/YoutubeExplode/YoutubeExplode.Demo.Gui/bin/Debug/net8.0/YoutubeExplode.Demo.Gui.dll

Build succeeded.
    0 Warning(s)
    0 Error(s)

Time Elapsed 00:01:02.58
➜  YoutubeExplode git:(master) dotnet test
  Determining projects to restore...
  All projects are up-to-date for restore.
  YoutubeExplode -> /Users/temp/git/YoutubeExplode/YoutubeExplode/bin/Debug/netstandard2.0/YoutubeExplode.dll
  YoutubeExplode -> /Users/temp/git/YoutubeExplode/YoutubeExplode/bin/Debug/netstandard2.1/YoutubeExplode.dll
  YoutubeExplode -> /Users/temp/git/YoutubeExplode/YoutubeExplode/bin/Debug/netcoreapp3.1/YoutubeExplode.dll
  YoutubeExplode -> /Users/temp/git/YoutubeExplode/YoutubeExplode/bin/Debug/net8.0/YoutubeExplode.dll
  YoutubeExplode -> /Users/temp/git/YoutubeExplode/YoutubeExplode/bin/Debug/net461/YoutubeExplode.dll
  YoutubeExplode.Converter -> /Users/temp/git/YoutubeExplode/YoutubeExplode.Converter/bin/Debug/netcoreapp3.1/YoutubeExplode.Converter.dll
  YoutubeExplode.Converter -> /Users/temp/git/YoutubeExplode/YoutubeExplode.Converter/bin/Debug/net8.0/YoutubeExplode.Converter.dll
  YoutubeExplode.Converter -> /Users/temp/git/YoutubeExplode/YoutubeExplode.Converter/bin/Debug/netstandard2.0/YoutubeExplode.Converter.dll
  YoutubeExplode.Converter -> /Users/temp/git/YoutubeExplode/YoutubeExplode.Converter/bin/Debug/net461/YoutubeExplode.Converter.dll
  YoutubeExplode.Tests -> /Users/temp/git/YoutubeExplode/YoutubeExplode.Tests/bin/Debug/net8.0/YoutubeExplode.Tests.dll
  YoutubeExplode.Converter -> /Users/temp/git/YoutubeExplode/YoutubeExplode.Converter/bin/Debug/netstandard2.1/YoutubeExplode.Converter.dll
Test run for /Users/temp/git/YoutubeExplode/YoutubeExplode.Tests/bin/Debug/net8.0/YoutubeExplode.Tests.dll (.NETCoreApp,Version=v8.0)
  YoutubeExplode.Converter.Tests -> /Users/temp/git/YoutubeExplode/YoutubeExplode.Converter.Tests/bin/Debug/net8.0/YoutubeExplode.Converter.Tests.dll
VSTest version 17.11.0 (x64)

Test run for /Users/temp/git/YoutubeExplode/YoutubeExplode.Converter.Tests/bin/Debug/net8.0/YoutubeExplode.Converter.Tests.dll (.NETCoreApp,Version=v8.0)
Starting test execution, please wait...
A total of 1 test files matched the specified pattern.
VSTest version 17.11.0 (x64)

Starting test execution, please wait...
A total of 1 test files matched the specified pattern.
[xUnit.net 00:00:16.27]     I can get a specific stream of a video(videoId: "rXMX4YJ7Lks") [SKIP]
  Skipped I can get a specific stream of a video(videoId: "rXMX4YJ7Lks") [1 ms]
[xUnit.net 00:00:24.08]     I can get a specific stream of a video(videoId: "SkRSXFQerZs") [SKIP]
[xUnit.net 00:00:24.08]     I can try to get the list of available streams of a video and get an error if it is paid [SKIP]
  Skipped I can get a specific stream of a video(videoId: "SkRSXFQerZs") [1 ms]
  Skipped I can try to get the list of available streams of a video and get an error if it is paid [1 ms]
[xUnit.net 00:00:34.95]     I can download a specific stream of a video(videoId: "rXMX4YJ7Lks") [SKIP]
  Skipped I can download a specific stream of a video(videoId: "rXMX4YJ7Lks") [1 ms]
[xUnit.net 00:00:59.94]     I can download a specific stream of a video(videoId: "SkRSXFQerZs") [SKIP]
  Skipped I can download a specific stream of a video(videoId: "SkRSXFQerZs") [1 ms]
[xUnit.net 00:01:11.94]     I can get the list of available streams of any playable video(videoId: "rXMX4YJ7Lks") [SKIP]
[xUnit.net 00:01:11.94]     I can get the list of available streams of any playable video(videoId: "SkRSXFQerZs") [SKIP]
  Skipped I can get the list of available streams of any playable video(videoId: "rXMX4YJ7Lks") [1 ms]
  Skipped I can get the list of available streams of any playable video(videoId: "SkRSXFQerZs") [1 ms]
[xUnit.net 00:01:59.34]     I can try to get the HTTP live stream URL for a video and get an error if it is not live [SKIP]
  Skipped I can try to get the HTTP live stream URL for a video and get an error if it is not live [1 ms]



Passed!  - Failed:     0, Passed:   160, Skipped:     8, Total:   168, Duration: 3 m 10 s - YoutubeExplode.Tests.dll (net8.0)

Passed!  - Failed:     0, Passed:    11, Skipped:     0, Total:    11, Duration: 3 m 8 s - YoutubeExplode.Converter.Tests.dll (net8.0)
```

