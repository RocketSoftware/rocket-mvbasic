# Change Log

## Version 1.1.0: March 31, 2021
- Initial release

## Version 1.1.1: May 27, 2021
- Add new feature: Signature Help
- Add new feature: Diagnostic

## Version 1.1.2: July 31, 2021
- Add new feature: Code Lens
- Bug fix: @ variables are recognized as undefined symbol
- Bug fix: catalog checking causes high CPU usage
- Bug fix: go to definition doesn't work correctly when cursor at the beginning of a symbol
- Bug fix: open single file in VS Code causes crash

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