# Test Pipeline

## Summary

Test pipelines for .NET and NodeJS projects.

## Version

![dotnet 8](https://img.shields.io/badge/net8.0-blue.svg)

## Pipeline Setup Instructions

1. Go to  [Azure DevOps](https://dev.azure.com/tbs-sct/GCExchange/_build) and create a new pipeline.
2. Connect to the repository in either GitHub or Azure Repos Git.
3. Configure the pipeline to any template, we will replace the code so it doesn't matter.
4. On the review step replace the code with one of the templates in this project, depending on if the project is nodeJS or .Net.
5. Rename the yml file to something meaningful like `unit-test-pipeline.yml` in the UI.

## .NET xUnit Setup Instructions

1. Right click your solution, `Add` -> `New Project...`
2. Select `Class Library`, set the location to the root of your repo, and name it `UnitTests`, choose `.NET 8`
3. Right click on `Dependencies` in the UnitTests project and click `Add Project Reference...`
4. Add a reference to your function app .csproj file, and hit OK
5. Add the following dependencies to your UnitTests project:
   - Microsoft.NET.Test.Sdk v17.11.1
   - xunit v2.9.3
   - xunit.runner.visualstudio v3.1.5
   - coverlet.collector v6.0.2
6. Your UnitTests.csproj file should look something like this when completed:
<img width="1002" height="434" alt="image" src="https://github.com/user-attachments/assets/b171357d-a85f-4efd-bcc0-f3163a868749" />
7. Add tests to a class inside your UnitTests project, [see the documentation here](https://learn.microsoft.com/en-us/dotnet/core/testing/unit-testing-csharp-with-xunit)

## Jest Setup Instructions (SPFx v1.21.1)

1. Add the following to `devDependencies` in `package.json`
   - `"jest": "^29.7.0"`
   - `"ts-jest": "^29.2.5"`
   - `"@types/jest": "^29.5.12"`
   - `"jest-environment-jsdom": "^29.7.0"`
   - `"@testing-library/react": "^12.1.5"`
   - `"@testing-library/jest-dom": "^5.17.0"`
2. In the project's root folder add the following:
   - `jest.config.js`
       - <img width="594" height="455" alt="image" src="https://github.com/user-attachments/assets/0109a1a1-8118-490a-9d71-a71559da096c" />
   - `jest.setup.js`
       - <img width="401" height="88" alt="image" src="https://github.com/user-attachments/assets/0b99d8a2-6965-4793-b032-90a65d2d7dd9" />
   - `tsconfig.jest.json`
       - <img width="468" height="388" alt="image" src="https://github.com/user-attachments/assets/72627b97-d16e-478d-b4a1-6092c86af99a" />
3. In the `src` folder add a folder called `src/__mocks__`
   - This is where you will mock file & data that the tests don't have access to at runtime.
4. Add tests to your project in the format `{ComponentName}.test.tsx`
   - In your `tsconfig.jest.json` the `root` property tells jest where to look for test files.
   - Any `.test.ts`, `.test.tsx`, `.spec.ts`, `.spec.tsx file`, or file inside a `__tests___ folder.
5. Once you have a test to try, run the command `npx jest --config jest.config.js` to test locally.
6. You can find further documentation [here](https://jestjs.io/docs/getting-started)

