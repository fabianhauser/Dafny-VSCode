# Dafny VSCode

This repository contains the infrastructure necessary to support _Dafny_ for Visual Studio Code.

* master: [![Build Status](https://travis-ci.com/DafnyVSCode/Dafny-VSCode.svg?branch=master)](https://travis-ci.com/DafnyVSCode/Dafny-VSCode)
* develop: [![Build Status](https://travis-ci.com/DafnyVSCode/Dafny-VSCode.svg?branch=develop)](https://travis-ci.com/DafnyVSCode/Dafny-VSCode)

## Architecture

The infrastructure consists of a _Dafny_ language server, which can be found in the [server](server/) directory, and a VS Code extension, which in turn can be found in the [client](client/) directory. These components communicate with each other using the [_Language Server Protocol (LSP)_](https://microsoft.github.io/language-server-protocol/).

## Contribute

We welcome all contributions! Please create a pull request and we will take care of releasing a new version when appropriate.

### How-To

It is pretty simple to contribute to this plugin. All it takes is having Visual Studio Code and npm installed. Simply clone this repository and switch into the new folder. On the command line, execute one of the following scripts:

* Linux & macOS: `./startup`
* Windows: `startup.bat`

These scripts do nothing else than execute the following commands:

* `cd server`
* `npm install`
* `code .`
* `cd ../client`
* `npm install`
* `code .`

Note: It is necessary that the `code` command is available in your `PATH`. On the Mac, this is usually not given. If it is missing, have a look at this [tutorial](https://code.visualstudio.com/docs/setup/mac).

If all the commands succeeded, the language server part and the client part of the plugin are opened in two different Visual Studio Code editors and installs all the dependencies. In the server editor, press `CTRL+Shift+b` or `⇧+⌘+B` to compile. The task that is started also watches file changes and recompiles automatically after saving.

To try out the changes, go to the client editor and press `F5`. A new instance of Visual Studio Code will be started that has the Dafny plugin running and ready for testing. Sometimes, Visual Studio Code does not recognize changes and does not apply them to the running test instance. If this is the case, simply close and restart the test instance, the changes should then be applied.

If you wish to contribute, simply make your changes and submit a pull request. Make sure that your changes don't break the existing tests in the client/test folder. You can run the tests with `npm test` while in the client folder. For this to work, you have to set environment variable `DAFNY_PATH` on your system to your _Dafny_ release (without a "/" at the end of the path). Feel free to add any tests.

Final note: Having the extension installed via the Visual Studio Marketplace (along with a _Dafny_ installation via the extension), can lead to conflicts with your locally built extension. It is therefore recommended to uninstall all previous installations of the extension from Visual Studio Code.

## Release

To release a new version of Dafny VSCode, follow the description in [RELEASE.md](RELEASE.md).
