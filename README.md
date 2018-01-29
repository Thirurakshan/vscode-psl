# vscode-psl

Profile Scripting Language functionality for Visual Studio Code.

![editor](https://raw.githubusercontent.com/tipleagame/vscode-psl-images/master/images/editor.png)

## Table of Contents

- [Dependencies](#dependencies)
- [Configuration](#configuration)
- [Features](#features)
	- [Host Commands](#host-commands)
	- [Language Support](#language-support)
	- [Host Terminal](#host-terminal)
- [Development](#development)


## Dependencies
* Visual Studio Code version 1.17 (October 2017) or higher 
* Java Runtime Environment 1.7 or higher (for Code Review)

## Configuration

Locate the button at the bottom-right corner titled `Configure Environments`. If the button is not visible, use the Command Pallete (<kbd>F1</kbd> or <kbd>Ctrl</kbd>+<kbd>Shift</kbd>+<kbd>P</kbd>) to find the `PSL: Configure Environment` command. A JSON object of the following form will appear:
```json
{
	"environments": [
		{
			"name": "",
			"host": "",
			"port": 0,
			"user": "",
			"password": "",
			"sshLogin": ""
		}
	]
}
```
Here you can store a global array of configurations. Use auto-complete and hover suggestions for hints about using the configuration file.

## Features

### Host Commands

The extension is able to communicate with Host via MRPC121. It can Get/Refresh from Host, Test Compile, Send to Host, Compile and Link, and Run PSL. 

These commands can be executed via:
*  The Command Pallette (<kbd>F1</kbd> or <kbd>Ctrl</kbd>+<kbd>Shift</kbd>+<kbd>P</kbd>)
*  Icons at the top-right corner of the document
*  Right-clicking the document
*  Right-clicking the file in the Side Bar Explorer

Please note that the Host Commands are executed *asynchronously*, meaning that vscode will not require you to wait to finish one action before you start another. This may have unintended consequences if you do not wait. For example, you must wait for sending to finish before you compile and link.

### Language Support

For files written in PSL, syntax highlighting with basic auto-completion is available. This includes completion items on core classes, such as String or Number, as well as completion for Record objects based on Column Definitions found in the `dataqwik/table` directory.

An **Outline** of a PSL file is also available via the keyboard shortcut <kbd>Ctrl</kbd>+<kbd>Shift</kbd>+<kbd>O</kbd>, or can be made visible by installing the [Code Outline](https://marketplace.visualstudio.com/items?itemName=patrys.vscode-code-outline) extension.

TBL and COL files have syntax highlighting, as well as auto-completion and hover information. These are defined in the `schemas` directory of the vscode-psl project.

DAT files will display hover information about an entry's column, based on the number of tabs in the row.

### Host Terminal

This extension adds to the vscode integrated terminal to allow quick-access to your configured Host server.

![terminal](https://raw.githubusercontent.com/tipleagame/vscode-psl-images/master/images/terminal.gif)

Visit the [wiki page](https://gitlab.ing.net/ProfileNL/vscode-psl/wikis/features/integrated-terminal) for complete documentation on the Integrated Host Terminal.

## Development

If you would like to join the development of this extension, you will need to install [node.js](https://nodejs.org/en/) (with NPM) in order to install the dependencies.

Once you clone the project, from the command line in the root of this project, run `npm install`. The ING network will likely restrict you from doing this, so you may have to switch to an open/guest network and run this command.

For ideas on features to implement, visit the below link:

https://code.visualstudio.com/docs/extensions/language-support
