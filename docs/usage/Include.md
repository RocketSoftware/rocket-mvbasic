## Include Settings

When a BASIC program includes some other files by using the `INCLUDE` statement, you can update the "includeMapping" setting in the configuration file so that the included file is referenced correctly.

Please refer to [Configuration](Configuration.md) for information on opening database related configuration files.

```json
"includeMapping": [
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

### Examples

Here are some examples to configure "includeMapping".

**Example 1**

Map folder "BP" in current account folder as "MAP_INC". BASIC statement may like:

```
$INCLUDE MAP_INC HEADER_NAME
```

The configuration is:

```json
"includeMapping": [
    {
        "includeFile": "MAP_INC", 
        "fileName": "BP"
    }
]
```

**Example 2**

If BASIC program includes file from another folder, for example, map "BP" in account "DEMO" as "MAP_INC", then the configuration is:

```json
"includeMapping": [
    {
        "includeFile": "MAP_INC", 
        "account": "DEMO", 
        "fileName": "BP"
    }
]
```

**Example 3**

Add multiple items in "includeMapping".

```json
"includeMapping": [
    {
        "includeFile": "MAP_INC", 
        "fileName": "BP"
    }, 
    {
        "includeFile": "MAP_ANOTHER_INC", 
        "account": "DEMO", 
        "fileName": "BP"
    }
]
```

