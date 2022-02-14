## Catalog Settings

Please refer to [Configuration](Configuration.md) to open the database related configuration file and then find the "catalog" section.

```
"catalog": {
    "readServerInternal": 5, 
    "isSearchAllDirs": false,
    "programDirs": [
        {
            "fileName": ""
        },
        {
            "account": "",
            "fileName": ""
        }
    ],
    "programMapping": [
        {
            "catalogName": "",
            "program": ""
        },
        {
            "catalogName": "",
            "fileName": "",
            "program": ""
        },
        {
            "catalogName": "",
            "account": "",
            "fileName": "",
            "program": ""
        }
    ]
}
```

- `readServerInternal`: the extension requests catalog related information from server per *X* seconds when connected to a U2 server. *X* is the value you set to this setting. By default *X* is 5 seconds. 
- `isSearchAllDirs`: specifies whether to search all sub-folders to find catalog programs in the current account folder. By default, the value is false, and only the folder containing the file current being edited is searched. If set to true, all sub-folders will be searched.
- `programDirs`: sets the account and folder in which to search for catalog files. You can add multiple items in this setting.
    - `fileName`: file folder name. 
    - `account`: account folder name.
- `programMapping`:
    - `catalogName`: catalog program name; sometimes this is different from the source code file name.
    - `program`: catalog program file name, which is the source code file name.
    - `account`: specifies the account that contains the catalog program file. You can configure multiple account folders in the configuration file. Please refer to [Accounts Settings](Accounts.md) for more details.
    - `fileName`: file folder name.

### Examples

**Example 1**. Search for catalog programs in another source code folder in the current account folder. For example, add a folder named "OtherFolder" to search for catalog programs in current account folder:

    "programDirs": [
        {
            "fileName": "OtherFolder"
        }
    ]

**Example 2**. Search for catalog programs in another account’s folders. For example, add the folder "OtherFolder" (from the “DEMO” account) to search for catalog program files:

    "programDirs": [
        {
            "account": "DEMO",
            "fileName": "OtherFolder"
        }
    ]

**Example 3**. Create a mapping relationship between the names of catalog programs and their source files. For example, to map the catalog program named "CtlgProgram" to the source code file named "SourceCode", the settings should be:

    "programMapping": [
        {
            "catalogName": "CtlgProgram",
            "program": "SourceCode"
        }
    ]

**Example 4**. Create a mapping relationship between the names of catalog programs and their source files, where the source code is in another account folder. For example, to map the catalog program named "CtlgProgram" to the source code file named "SourceCode" (which exists in the “BP” file folder of the "DEMO" account ), the settings should be:

```
"programMapping": [
    {
        "catalogName": "CtlgProgram",
        "file": "BP", 
        "program": "SourceCode"
    }
]
```

**Example 5**. Create a mapping relationship between the names of catalog programs and their source files, where the source code file is in another file folder of the current account. For example, to map the catalog program named "CtlgProgram" to the source code file named "SourceCode" (which exists in the “BP”folder), the settings should be:

```
"programMapping": [
    {
        "catalogName": "CtlgProgram",
        "account": "DEMO"
        "file": "BP", 
        "program": "SourceCode"
    }
]
```

