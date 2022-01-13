# Test Solution for Code Commenter

Solution which provides a collection of empty files of different formats, allowing easy testing of the code commenter extension.

- [File Structure](#file-structure)
- [Projects](#projects)
- [Utilization](#utilization)

## File Structure

There are two levels of `.editorconfig` files which are utilized by the various projects:

- The root level `.editorconfig` which all files look to
  - This uses space tabs, with an indentation/tabsize of 3 spaces
- A secondary `.editorconfig` underneath the respective `\SecondaryEditorConfig` directories which only applies to files underneath
  - This uses actual tab characters, with an indentation/tabsize of 5 spaces

The code commenter should be able to utilize contextual settings to pull the appropriate indent/tabsize for each specific file.

## Projects

- `CSharpTestFiles`
  - Test projects which holds C# test files (required because the Roslyn compiler, which the C# formatter relies on, only works in C# projects)
  - Contains code which utilizes the main `.editorconfig` under `\BaseEditorConfig`
  - Contains code which utilizes the secondary `.editorconfig` under `\SecondaryEditorConfig`
- `CTestFiles`
  - Test project which primarily holds C test files
  - Also holds Python/Xml/Javascript test files
  - Contains code which utilizes the main `.editorconfig` under `\BaseEditorConfig`
  - Contains code which utilizes the secondary `.editorconfig` under `\SecondaryEditorConfig`

## Utilization

You can easily debug the `Code Commenter` project by providing a path to this solution and the `/rootsuffix Exp` argument, ala:

- `"C:\src\code-commenter-tester\CodeCommenterTester.sln /rootsuffix Exp`

This will run an instance of the solution with only that extension installed.
