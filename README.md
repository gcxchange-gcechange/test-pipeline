# Test Pipeline

## Summary

Test pipelines for .NET and NodeJS projects.

## Version

![dotnet 8](https://img.shields.io/badge/net8.0-blue.svg)

## .Net xUnit Setup Instructions

1. Right click your solution, `Add` -> `New Project...`
2. Name the new project `UnitTests`, choose `.NET 8`
3. Right click on `Dependencies` in the UnitTests project and click `Add Project Reference...`
4. Add a reference to your function app .csproj file, and hit OK
5. Add the following dependencies to your UnitTest project:
   - Microsoft.NET.Test.Sdk v17.11.1
   - xunit v2.9.3
   - xunit.runner.visualstudio v3.1.5
   - coverlet.collector v6.0.2
6. Your UnitTests.csproj file should look something like this when completed:
<img width="1002" height="434" alt="image" src="https://github.com/user-attachments/assets/b171357d-a85f-4efd-bcc0-f3163a868749" />
7. Add tests to a class inside your UnitTests project, see further instructions [here](https://learn.microsoft.com/en-us/dotnet/core/testing/unit-testing-csharp-with-xunit)


## Pipeline Setup Instructions

1. Go to  [Azure DevOps](https://dev.azure.com/tbs-sct/GCExchange/_build) and create a new pipeline.
2. Connect to the repository in either GitHub or Azure Repos Git.
3. Configure the pipeline to any template, we will replace the code so it doesn't matter.
4. On the review step replace the code with one of the templates in this project, depending on if the project is nodeJS or .Net.
5. Rename the yml file to something meaningful like `unit-test-pipeline.yml` in the UI.

## Ignore Packages (Frontend Only)

Follow these steps to ignore specific npm packages during the npm audit.

1. Add a file named `ignored-packages.txt` in the same directory as your .yml file.
2. Add each package that should be ignored on its own line within the file.
3. Save and run the pipeline.
<img width="235" height="183" alt="image" src="https://github.com/user-attachments/assets/c4e223b6-af71-4736-a061-07ce05e1f180" />
