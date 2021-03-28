## Using Definition

Use following methods to find a symbol's definition:

- Right click a symbol then select `Goto Definition`;
- Move cursor to a symbol then press <kbd>F12</kbd>;
- Press and hold <kbd>Ctrl</kbd> button and click a symbol.

For some special symbols, you need do some configuration before using this functionality.

### CALL Statement

There are several different cases when you use  `Goto Definition` on `CALL` statement / catalog programs to find its source code.

#### Not Connected to U2 Server

If the cataloged program is in the same folder as the currently opened file, the target file can be opened directly.

If the cataloged program is in another sub-folder of the current account folder, you can do one of the following:

- Set `isSearchAllDirs` to `true` in the configuration file.
- Add the sub-folder name to the `programDirs` element in the configuration file.

Please refer to [Catalog settings](Catalog.md) for instructions on how to setup this configuration.

If the cataloged program source code is in another account folder, you can:

- add the account folder to the configuration file. Please refer [Accounts settings](Accounts.md).
- add catalog program mapping settings to the `programMapping` element in the configuration file. Please refer to [Catalog settings](Catalog.md) for instructions on how to setup this configuration.

#### Connected to U2 Server

When connected to a MultiValue server, `Goto Definition` can fetch catalog programs from the server to the local machine. Please refer to [Connection settings](Connection.md) for instructions on how to connect to a U2 server.

For *local cataloged programs*, if the cataloged program name is the same as its source code file name, use Goto Definition directly. If the cataloged program name is different from its source code file name, you will need set the mapping relationship between cataloged program name and its source code name. Please refer to [Catalog settings](Catalog.md) to configure the mapping relationship.

For *global cataloged programs*, you need configure the global catalog program information which includes the account name and names mapping. Please refer to [Catalog settings](Catalog.md) and [Account settings](Accounts.md) for more details.

### INCLUDE Statement

If the current opened file includes some other files through the INCLUDE statement, you can use `Goto Definition` to jump to a symbol's definition in the included file. Please refer to [Include settings](Include.md) to setup the related configuration.

