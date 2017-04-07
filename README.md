# WinSWAG: **Win**dows **s**ervice **w**rapper (**a**nother **g**eneration).

[![Github All Releases](https://img.shields.io/github/downloads/ankobi/winswag/total.svg)](https://github.com/ankobi/winswag/releases)

WinSWAG is an executable binary, which can be used to wrap and manage a custom process as a Windows service.
Once you download the installation package, you can rename `WinSWAG.exe` to any name, e.g. `myService.exe`.

Forked from [kohsuke/winsw](https://github.com/kohsuke/winsw). The original version was available for .NET Frameworks `2.0` and `4.0` as targets, which was not suitable for my use case. This version was build with .NET Frameworks `4.5.2`.

I removed all executable signing and "cleaned" up the solution to my needs, removing the additional .NET `4.0` project and updating the existing projects to `4.5.2`.

## Usage

WinSW is being managed by configuration files: [Main XML Configuration file](doc/xmlConfigFile.md) and [EXE Config file](doc/exeConfigFile.md).

Your renamed `WinSWAG.exe` binary also accepts the following commands:

* `install` to install the service to Windows Service Controller.
  This command requires some preliminary steps described in the [Installation Guide](doc/installation.md).
* `uninstall` to uninstall the service. The opposite operation of above.
* `start` to start the service. The service must have already been installed.
* `stop` to stop the service.
* `restart` to restart the service. If the service is not currently running, this command acts like `start`.
* `status` to check the current status of the service.
* This command prints one line to the console.
* `NonExistent` indicates the service is not currently installed
* `Started` to indicate the service is currently running
* `Stopped` to indicate that the service is installed but not currently running.

## Documentation

* [Installation Guide](doc/installation.md) - Describes the installation process for different systems and .NET versions
* [Release notes](CHANGELOG.md)
* Configuration:
  * [Main XML Configuration file](doc/xmlConfigFile.md)
  * [EXE Configuration File](doc/exeConfigFile.md)
  * [Logging and Error Reporting](doc/loggingAndErrorReporting.md)
  * [Extensions](doc/extensions/extensions.md)
* Use-cases:
  * [Self-restarting services](doc/selfRestartingService.md)
  * [Deferred File Operations](doc/deferredFileOperations.md)
* Configuration Management:
  * [Puppet Forge Module](doc/puppetWinSW.md)