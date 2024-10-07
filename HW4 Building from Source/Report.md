
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


