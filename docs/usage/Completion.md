## Using Auto-Completion

When editing a BASIC program, the auto-completion function can prompt and complete what is currently being edited according to the contextual environment. The completion includes:

 - Statements and keywords
 - Symbols, functions, subroutines, labels, etc;
 - File names and program names

For some special BASIC statements, auto-completion also has some advanced functionality:

- `CALL statement`

  If you do not connect to a MultiValue server, catalog names in CALL statements can be completed based on the currently opened account folder. Please refer to [Catalog settings](Catalog.md).

  If you connect to a MultiValue server, the extension can get all catalog program names from the server and list them. To connect to a MultiValue server, please refer to [Connection settings](Connection.md).

- `INCLUDE statement`

  In the INLCUDE statement, the auto-completion function can complete the file name and program name in the statement.

  By default, only the file names and program names in the current account folder can be auto completed, but you can add additional account folders by modifying the configuration file, so that when you are typing INCLUDE statements, the file names and program names from the additional accounts will also be prompted.

  Please refer to [Accounts settings](Accounts.md) and Include section for more details. (note … no link present for Include section)

