## Include Settings

When a BASIC program includes some other files by using the `INCLUDE` statement, you can update the includes setting in the configuration file so that the included file is referenced correctly.

Please refer to [Configuration](Configuration.md) for information on opening database related configuration files.

```json
"includes": [
    {
        "includeFile": "",
        "account": "", 
        "fileName": ""
    }
]
```

- `includeFile`: the file name in the `INCLUDE` statement.
- `account`: account folder name. Please refer to [Accounts settings](Accounts.md) to add account folders.
- `fileName`: file folder name. The file folder should contain BASIC programs.