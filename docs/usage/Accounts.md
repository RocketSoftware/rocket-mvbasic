## Accounts Settings

You can add additional account folders in the configuration file. Doing this allows other features to reference the source code in these account folders.

**Note**: the account folders must be on your local machine.

Please refer to  [Configuration](Configuration.md) to open the database related configuration file.

```
"accounts": [
    {
        "name": "accountName",
        "path": "accountFullPath"
    }
]
```

Find the "accounts" section and then add your additional accounts.

- `name`: the account name.

- `path`: the account folders full path.

You can also add multiple accounts settings.

```
"accounts": [
    {
        "name": "accountName_1",
        "path": "accountFullPath_1"
    }, 
    {
    	"name": "accountName_2", 
    	"path": "accountFullPath_2"
    }
]
```

