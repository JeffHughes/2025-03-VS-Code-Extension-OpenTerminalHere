# Open Terminal Here

A simple VS Code extension that adds a right-click option to open a terminal from the selected folder in the file explorer and adds a keyboard shortcut for opening a terminal at the current file's directory.

## Features

- Right-click on any folder or file in the Explorer view and select "Open Terminal Here" to open a terminal at that location
- Use the keyboard shortcut `Ctrl+Shift+T` to open a terminal at the directory of the currently active file

## Requirements

- VS Code 1.60.0 or higher

## Installation

### From VSIX file

1. Download the `.vsix` file from the releases
2. Open VS Code
3. Go to Extensions view (Ctrl+Shift+X)
4. Click on the `...` menu in the top-right of the Extensions view
5. Select "Install from VSIX..."
6. Navigate to the downloaded `.vsix` file and select it

### From source

1. Clone this repository
2. Run `npm install` to install dependencies
3. Run `npm run package` to create a `.vsix` file
4. Follow the steps above to install the extension from the VSIX file

## Usage

### Context Menu

1. Right-click on any folder or file in the Explorer view
2. Select "Open Terminal Here" from the context menu
3. A new terminal will open with the working directory set to the selected location

### Keyboard Shortcut

1. Open any file in the editor
2. Press `Ctrl+Shift+T`
3. A new terminal will open with the working directory set to the directory of the active file

## Extension Settings

This extension contributes the following settings:

* `workbench.action.terminal.newWithCwd`: Command used by the keyboard shortcut to open a terminal at the current file's directory

## Known Issues

None at this time.

## Release Notes

### 1.0.0

Initial release of Open Terminal Here
- Add right-click context menu option to open terminal at selected location
- Add keyboard shortcut to open terminal at current file's directory
