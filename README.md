# VSIXInteropFormsToolkit
Visual Studio extension, with command tool to generate interop wrapper classes. adapted from add-in.

 * [VSIXInteropFormsToolkit in Visual Studio Marketplace](https://marketplace.visualstudio.com/items?itemName=filiperoque.VSIXInteropFormsToolkit) 

See:

 * [VB6 - C# Interop Form Toolkit](http://www.codeproject.com/Articles/15690/VB-C-Interop-Form-Toolkit)
 * [Interop Forms Toolkit 2.0 Tutorial](http://www.codeproject.com/Articles/18954/Interop-Forms-Toolkit-Tutorial)
 * [Microsoft InteropForms Toolkit 2.1](https://www.microsoft.com/en-us/download/details.aspx?id=3264)
 * [Interop Forms Toolkit for C#](https://interoptoolkitcs.codeplex.com) (also imported to https://github.com/froque/interoptoolkitcs)
 * [Similar extension in Visual Studio Marketplace](https://marketplace.visualstudio.com/items?itemName=MiguelLe.MicrosoftInteropFormToolsInteropFormProxyGenerator) ([source code](https://github.com/hurcane/Microsoft.InteropFormTools.InteropFormProxyGenerator))

### Microsoft InteropForms Toolkit 2.1 Documentation

* [Microsoft InteropForms Toolkit 2.1 Online Documentation](http://froque.github.io/VSIXInteropFormsToolkit/)

### Info
At present state this tool does not override files previously generated. 
When forms with unsupported parameter types are found, the initialize method will be generated with a parameter with the root type "Object".

### Supported Environments

 * Visual Studio 2015
 * Visual Studio 2017

### How to Debug 

Open project properties
- choose Debug
- In Start Action 
	- choose "Start external program"
	- and write path to visual studio. (Ex: `C:\Program Files (x86)\Microsoft Visual Studio 14.0\Common7\IDE\devenv.exe`)
- On Command line arguments "/rootsuffix Exp"
- Start application
- Create project in newly opened VS window
- Run tool


## Upgrade
 * [How to: Update a Visual Studio Extension](https://msdn.microsoft.com/en-us/library/dd997169.aspx)
   * edit version in source.extension.vsixmanifest
   * compile project
   * upload .vsix file to [Visual Studio Marketplace](https://visualstudiogallery.msdn.microsoft.com/)
 
## Compile from console
	nuget restore VSIXInteropFormsToolkit.sln
	"C:\Program Files (x86)\MSBuild\14.0\Bin\MSBuild.exe" /t:Clean /p:Configuration=Release "VSIXInteropFormsToolkit.sln"
	"C:\Program Files (x86)\MSBuild\14.0\Bin\MSBuild.exe" /p:Configuration=Release "VSIXInteropFormsToolkit.sln"
