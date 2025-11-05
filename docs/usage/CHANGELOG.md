# Change Log

## Version 2.8.0: November 05, 2025
 - Support for TRY-CATCH syntax introduced in UV 14.2.1
 - Support for dynamic object syntax introduced in UV 14.2.1
 - Support for hashed file record operations like Edit, update, and delete records and Optimistic locking for concurrent access
 - Support for optimistic and pessimistic locking mechanisms on file
 - Customer Bug fixes

## Version 2.7.1: June 04, 2025
 - Added VS Code language auto-detection (online mode)
 - Auto-close files on server disconnect in online mode
 - Customer bug fixes

## Version 2.7.0: April 22, 2025
 - Separate compile and catalog option
 - Support for debugging BASIC program files in online editing mode. (support with UV 11.4.1 and upcoming 14.2.1)
 - Support for keyword search within U2 accounts via right-click context menu.
 - Customer bug fixes

## Version 2.6.0: November 21, 2024
 - Enhancement: UD compilation will read parameters from basic.mvbasic.json file.
 - Support pattern configuration for account, folder and file filtering (only in online mode).
 - Customer bug fixes
  
## Version 2.5.1: August 23, 2024

 - Support for cataloging BASIC program files via right-click component in both online and offline modes.

## Version 2.5.0: June 26, 2024

 - Support compile / catalog BASIC program files in online editing mode.
 - Support the rpc service name can be customized (only in offline mode)
 - Customer bug fixes - some incorrect behaviors on Linux

## Version 2.4.0: February 26, 2024

 - Support high performance  debugging on UniData 8.3.1 (Windows / Linux).
 - Support new compilation flavor 'r' and 'm' for UniData.
 - Resolve the issue that extension could not be started when _JAVA_OPTIONS_ is configured.

## Version 2.3.0: October 31, 2023

 - Implement the ability to sort BASIC program files while in online editing mode.
 - Provide support for configuring unique server names for online editing servers.
 - Enhance warning messages for specific operations.
 - Implement various optimizations for the online editing mode.

## Version 2.2.0: August 17, 2023

- Support high performance debugging on UniVerse 11.4.1 (Windows / Linux)

## Version 2.1.0: May 31, 2023

- Support online editing (preview) which can help user to edit BASIC program files on remote U2 servers.

## Version 1.10.1: March 30, 2023

- Update extension's logo.

## Version 1.10.0: March 30, 2023

 - Enhancement: full path support in UniData $INCLUDE statement
 - Enhancement: disconnect debug session when U2 server is disconnected.
 - Enhancement: add functions / labels / subroutines to breadcrumbs.
 - Bugs fix: 6 bugs fixed.

## Version 1.9.0: January 5, 2023

 - Enhancement: support additional parameters for compilation
 - Enhancement: support additional parameters for debugging

## Version 1.8.0: October 27, 2022

- Feature: support logging system. Please refer online documentation for details.
- Feature: monitor U2 server connection status.
- Enhancement: when compiling a BASIC program, the account folder name must be the same as the connected account name.
- Bug fix: 38 bugs fixed.

## Version 1.7.0: August 17, 2022

- Feature: (Preview) support debugging functionalities on UniData 8.2.4. 
- Bug fix: improve the stability of debugging.
- Bug fix: improve file parsing performance.

## Version 1.6.0: April 29, 2022

- Feature: (Preview) support debug BASIC program files on UniVerse. Please refer online documentation to see known issues.
- Bug fix: show connection icon only when extension activated. 

## Version 1.5.0: March 31, 2022

- Feature: support multiple workspace folders.
- Enhancement: change some functions to support multiple workspace folders, for example, auto group view, connection to U2 server, etc.
- Bug fix: resolve incorrect syntax checking, for example, label name, REM function, etc.
- Bug fix: resolve a compilation failed issue if VS Code upgraded to latest version.
- Bug fix: make some messages more readable.
- Bug fix: support more UV and UD keywords.
- Bug fix: fix the issue formatting sometimes could not work.

## Version 1.4.0: January 28, 2022

- Enhancement: show U2 server account name when connection established.
- Bug fix: resolve some incorrect grammar / syntax related bugs.
- Bug fix: resolve some incorrect / misspelling messages.

## Version 1.3.3: December 21, 2021

- Upgrade log4j to 2.17.0 to avoid security issue.

## Version 1.3.2: December 17, 2021

- Upgrade log4j to 2.16.0 to avoid security issue.

## Version 1.3.1: December 11, 2021

- Upgrade log4j to latest version to prevent remote injection attack.

## Version 1.3.0: December 10, 2021

- Show U2 server connection status icon in status bar.
- Enhancement: more readable connection and compilation feedback messages.
- Bug fix: code folding error in loop statement.
- Bug fix: add missed functions and statements, for example: COM, TTYSET, XDOMGetElementById, etc.
- Bug fix: CALL @VARIABLE shows undefined function error.
- Bug fix: exclude objective code from compilation tasks in UniData;
- Bug fix: show overwriting message when modifying configuration files.
- Bug fix: update incorrect comments in configuration files.
- Bug fix: BASIC parser crashes when meets double special characters at head of a line.

## Version 1.2.0: September 30, 2021

- Support compile and catalog BASIC program files on U2 server;
- Add comments in configuration files for new created project;
- Select "UniVerse" or "UniData" when open the project first time, rather than set "UniVerse" as default;
- Optimize activation process: the extension now could be activated automatically when ".rmv" folder exists;
- Add commands to enable / disable code lens in current project, by default code lens is disabled;
- Bug fix: highlight U2 internal @ variables and don't show error for them;
- Bug fix: display one file multiple times in group view;
- Bug fix: improve performance when project is too big;
- Bug fix: unrecognized grammar for "LOOP WHILE READNEXT";
- Bug fix: provide hover documents for MQ related functions;
- Bug fix: support function HMAC.

## Version 1.1.2: July 31, 2021

- Add new feature: Code Lens
- Bug fix: @ variables are recognized as undefined symbol
- Bug fix: catalog checking causes high CPU usage
- Bug fix: go to definition doesn't work correctly when cursor at the beginning of a symbol
- Bug fix: open single file in VS Code causes crash

## Version 1.1.1: May 27, 2021

- Add new feature: Signature Help
- Add new feature: Diagnostic

## Version 1.1.0: March 31, 2021

- Initial release
