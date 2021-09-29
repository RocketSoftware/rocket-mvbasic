## About The Project

Rocket MV BASIC for VS code is a free Visual Studio Code Extension created by Rocket Software. The purpose of this extension is to enable BASIC developers to develop MV BASIC applications in one of the most popular development platforms- Microsoft Visual Studio Code. Rocket MV BASIC for VS code provides users with an exceptional editing experience.

## Features

This extension includes the following features:

 - BASIC statements / keywords highlighting
 - Semantic highlighting
 - Symbols collection / outline on the current document
 - Code folding
 - Go to / Peek definition on the current document or crossing different files
 - Rename symbols for the same type
 - Find symbol references in current document and crossing different files
 - Hover over a statement to display its documentation
 - Document formatting, range formatting and on typing formatting
 - Detail settings for formatting
 - Auto-Completion for BASIC statements, keywords, and symbols
 - Connect to U2 MultiValue server and cache cataloged programs to local machine when necessary
 - Auto-Group files and customize the group rules
 - Add customized documentation for functions, subroutines, or labels
 - Show syntax and grammar errors
 - Prompt parameters of BASIC internal functions
 - Compile / Catalog BASIC programs on the U2 server

## Restriction

Currently, the extension can only be used to edit BASIC program files on the machine where the VS Code installed, it does not support editing BASIC program files on remote servers directly. 

## Quick Start

Requirements: [VS Code](https://code.visualstudio.com/) 1.50 or higher version is required.

  1. Install this extension from the VS Code Marketplace.

  2. Download, install and setup the Java environment. Note that you can skip Step 1 and Step 2 if you already have Java 11+ (OpenJDK or Oracle JDK) installed. 

	*Step 1*: Download the Open JDK 11 or above GA releases zip file from [this page](http://jdk.java.net/archive/).

	*Step 2*: Unzip the downloaded zip file to a temporary location on your system (for example, "*C:\ThirdParty\open-jdk-11*").

	*Step 3*.  Open User Settings (use the appropriate option listed below):

	**On Windows/Linux**

	- File > Preferences > Settings

	- Use the keyboard shortcut <kbd>Ctrl</kbd> + <kbd>,</kbd> to open the setting editor 

	- Press <kbd>F1</kbd> or <kbd>Ctrl</kbd> + <kbd>Shift</kbd> + <kbd>P</kbd> to open the Command Palette, and then select `Preferences: Open Settings (UI)`

	**On macOS** 

	- Code > Preferences > Settings

	- Press <kbd>F1</kbd> or <kbd>Ctrl</kbd> + <kbd>Shift</kbd> + <kbd>P</kbd> on Mac to open Command Palette, and then select `Preferences: Open Settings (UI)`

	*Step 4*. Search “Rocket” to locate the Rocket MV BASIC extension and enter the Java bin path as illustrated in the example below.
	
	![](./img/readme_config.png)

	**Note**: Using this method, an existing working environment that requires a different version of Java would not be impacted and the extension will work properly in the Java 11 (or above) environment.

  3. Select "File" > "Open Folder" to pen a folder that contains the BASIC program files you want to view or edit. We recommend that you open the U2 account level folder to avoid encountering exceptions.

	**Note**: Multiple workspace folders are not supported yet. Because of this, ensure that you open only one workspace folder. This extension is designed to work with folders/directories rather than individual program files. If you open a single file, some functions may be limited.

  4. Activate the extension.

    - By default, the extension is automatically activated when opening a file with the suffix ".B". If your BASIC program files don’t end with a ".B" suffix, please refer to the FAQ to see how to customize the rules for activating the extension automatically.
    - If the extension is not activated automatically, please open the *Command Palette* in VS code(use any option listed below), and enter the "Activate Rocket MV BASIC" command to activate it manually.  
    
        **On Windows/Linux**
    
        - View > Command Palette
    
        - Press <kbd>F1</kbd> or <kbd>Ctrl</kbd> + <kbd>Shift</kbd> + <kbd>P</kbd>
    
        **On macOS**
    
        - View > Command Palette
    
        - Press <kbd>F1</kbd> or <kbd>Ctrl</kbd> + <kbd>Shift</kbd> + <kbd>P</kbd>
    
    **Note**: Currently, the extension does not provide version control capabilities. Users should manage source code versions independent of this extension.

## Usage

Click the links below to learn more about using each feature. You can also refer to the user manual [documentation online](https://rocketsoftware.github.io/rocket-mvbasic/).

**Editing Features**

- [Auto completion](./usage/Completion.md)
- [Code folding](./usage/Folding.md)
- [Code lens](./usage/CodeLens.md)
- [Document symbols](./usage/DocumentSymbol.md)
- [Diagnostics](./usage/Diagnostics.md)
- [Find references](./usage/References.md)
- [Formatting](./usage/Formatting.md)
- [Go to definition](./usage/Definition.md)
- [Hover](./usage/Hover.md)
- [Rename](./usage/Rename.md)
- [Semantic highlighting](./usage/SemanticHighlighting.md)
- [Signature help](./usage/SignatureHelp.md)

**Development Environment**

- [Auto group view](./usage/GroupView.md)
- [Compile BASIC programs](./usage/Compile.md)
- [Configurations](./usage/Configuration.md)
- [Connect to U2 server](./usage/Connection.md)
- [Customized documentation](./usage/CustomizeDoc.md)

## Contact Us

Please visit our [forum](https://community.rocketsoftware.com/forums/multivalue?CommunityKey=521bce2e-71d5-4d32-b560-dfa95e950eb5) for more information.