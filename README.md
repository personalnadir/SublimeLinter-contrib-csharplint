SublimeLinter-contrib-csharplint
================================

[![Build Status](https://travis-ci.org/SublimeLinter/SublimeLinter-contrib-csharplint.svg?branch=master)](https://travis-ci.org/SublimeLinter/SublimeLinter-contrib-csharplint)

A linter(software) called 'csharplint' does not exist, this simply uses Mono or the default .NET framework available on Windows in error checking mode.

![C# error example](https://lh5.googleusercontent.com/-8SLnmiT3Uzw/VD1Wzt1czQI/AAAAAAAABbg/a63CSip0xt0/w813-h396-no/csharplinter.png)

![Unity C# Warning](https://lh4.googleusercontent.com/-9TlxxCqwPoU/VD1Wzhr9PhI/AAAAAAAABbc/9gxZ9ViXMMc/w895-h398-no/unitycsharplinter.png)

## Installation
SublimeLinter 4 must be installed in order to use this plugin. If SublimeLinter 4 is not installed, please follow the instructions [here][installation].

### Linter installation
Before using this plugin, you must ensure that Mono or the default .NET framework is installed on your system. Mono installations that come with software may also be used, like in the case of Unity 3D.

### Linter configuration
In order for `csharplint` to be executed by SublimeLinter, you must ensure that its path is available to SublimeLinter. Before going any further, please read and follow the steps in [“Finding a linter executable”](http://sublimelinter.readthedocs.org/en/latest/troubleshooting.html#finding-a-linter-executable) through “Validating your PATH” in the documentation.

Once you have installed and configured `csharplint`, you can proceed to install the SublimeLinter-contrib-csharplint plugin if it is not yet installed.

Currently the package is set very specifically for a Window's user and has no configuration options. Please modify at the linter.py file according to your needs.

### Plugin installation
This package is not an official SublimeLinter package hence the 'contrib' notation and also not added to the main Package repository. You may add this Git as the repository.

Please use [Package Control][pc] to install the linter plugin. This will ensure that the plugin will be updated when new versions are available. If you want to install from source so you can modify the source code, you probably know what you are doing so we won’t cover that here.

To install via Package Control, do the following:

1. Within Sublime Text, bring up the [Command Palette][cmd] and type `add repository`. Among the commands you should see `Package Control:Add Repository`. Select it. Then enter https://github.com/Pendrokar/SublimeLinter-contrib-csharplint

1. Within Sublime Text, bring up the [Command Palette][cmd] and type `install`. Among the commands you should see `Package Control: Install Package`. If that command is not highlighted, use the keyboard or mouse to select it. There will be a pause of a few seconds while Package Control fetches the list of available plugins.

1. When the plugin list appears, type `csharplint`. Among the entries you should see `SublimeLinter-contrib-csharplint`. If that entry is not highlighted, use the keyboard or mouse to select it.

## Settings
For general information on how SublimeLinter works with settings, please see [Settings][settings]. For information on generic linter settings, please see [Linter Settings][linter-settings].

## Using with Unity

In order to run csharplint with Unity you will need to add the "completesharp_assemblies" list to your csharplint entry in the Sublime Linter settings. These will be platform dependent.

On Windows your unity path will resemble:

C:\\Program Files\\Unity\\Editor\\Data\\Managed\\

On Mac OS:

/Applications/Unity/Hub/Editor/2019.1.10f1/Unity.app/Contents/

Bear in mind that Unity Hub will install Unity in different locations based on the version number.

<pre><code>
"completesharp_assemblies": [
    "<b><i>unity path</i></b> Managed/UnityEngine.dll",
    "<b><i>unity path</i></b> Managed/UnityEditor.dll",
    "<b><i>unity path</i></b> Mono/lib/mono/unity/UnityScript.dll",
    "<b><i>unity path</i></b> Mono/lib/mono/unity/System.Core.dll",
    "<b><i>unity path</i></b> Mono/lib/mono/unity/System.dll",
    "<b><i>unity path</i></b> Mono/lib/mono/unity/mscorlib.dll",
    "<b><i>unity path</i></b> Mono/lib/mono/2.0/nunit.framework.dll",
    "<b><i>unity project path</i></b> Library/ScriptAssemblies/Assembly-CSharp.dll",
    "<b><i>unity project path</i></b> Library/ScriptAssemblies/Assembly-CSharp-Editor.dll",
    "<b><i>unity project path</i></b> Library/ScriptAssemblies/Assembly-UnityScript.dll",
    "<b><i>unity project path</i></b> Library/ScriptAssemblies/Assembly-CSharp-firstpass.dll"
]
</pre></code>

e.g.:

<pre><code>
"completesharp_assemblies": [
    "/Applications/Unity/Hub/Editor/2019.1.10f1/Unity.app/Contents/Managed/UnityEngine.dll",
    ...
]
</pre></code>


## Contributing
If you would like to contribute enhancements or fixes, please do the following:

1. Fork the plugin repository.
1. Hack on a separate topic branch created from the latest `master`.
1. Commit and push the topic branch.
1. Make a pull request.
1. Be patient.  ;-)

Please note that modications should follow these coding guidelines:

- Indent is 4 spaces.
- Code should pass flake8 and pep257 linters.
- Vertical whitespace helps readability, don’t be afraid to use it.
- Please use descriptive variable names, no abbrevations unless they are very well known.

Thank you for helping out!

[docs]: http://sublimelinter.readthedocs.org
[installation]: http://sublimelinter.readthedocs.org/en/latest/installation.html
[locating-executables]: http://sublimelinter.readthedocs.org/en/latest/usage.html#how-linter-executables-are-located
[pc]: https://sublime.wbond.net/installation
[cmd]: http://docs.sublimetext.info/en/sublime-text-3/extensibility/command_palette.html
[settings]: http://sublimelinter.readthedocs.org/en/latest/settings.html
[linter-settings]: http://sublimelinter.readthedocs.org/en/latest/linter_settings.html
[inline-settings]: http://sublimelinter.readthedocs.org/en/latest/settings.html#inline-settings
