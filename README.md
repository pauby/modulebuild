# A Module Build Script & Helpers

To use this build script you need:

* [Invoke-Build module](https://github.com/nightroman/Invoke-Build) (install it from the [PSGallery](https://www.powershellgallery.com/packages/InvokeBuild) using `Install-Module -Name InvokeBuild`

* A specific project folder structure

## Folder Structure

This build script expects your folder structure to be as follows:

```
PROJECT root
 |_ source
 |   |_ public
 |   |   |_ other folders (Optional)
 |   |
 |   |_ private (Optional)
 |   |   |_ other folders (Optional)
 |   |
 |   |_ PROJECT.psm1
 |   |_ PROJECT.psd1
 |
 |_ tests
 |   |_ public
 |   |_ private (optional)
 |
 |_ CHANGELOG.md
 |_ PROJECT.build.ps1
 |_ build.ps1
```

* `source` folder contains your source code script files. Under the public / private folders you can have additional folders containing script files;
* `tests` folder contains the Pester tests;
* `CHANGELOG.md` contains your version information with the latest version at the top of the file in the format `## v<MINOR.MAJOR.PATCH VERSION> <COMMENT>` (eg. `## v1.0.0 Initial Release`)

## Build Scripts

### PROJECT.build.ps1
Contains your build configuration and must dot source the build.ps1 script. When you run `Invoke-Build` this is the script that will be run first;

### build.ps1
This is the main `Invoke-Build` script. The latest version of this can always be found here.

## Test Scripts

### FUNCTION.Tests.ps1
This should contain the unit testing Pester tests for the FUNCTION. Note the Contextx / Categories of tests.

### SharedTestHelper.ps1
This script helps to import modules and the code being separated into it's own script allows reusability. The latest version of this can always be found here.

## Contributing to PSCodeHealth

You are welcome to contribute to this project. There are many ways you can contribute:

1. Submit [issues](/issues);
2. Submit a fix for an issue;
3. Submit a feature request;
4. Submit test cases;
5. Tell others about the project;
6. Tell the developers how much you appreciate the project!