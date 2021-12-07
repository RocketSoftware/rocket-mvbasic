## U2 Connection Settings

The Rocket MV BASIC extension can also connect to a U2 server. Regardless of whether you are connected to a server or not, all editor functions will work as expected. But when connected to a U2 server, some functions will have advanced capabilities. 

**Note**: you cannot edit program files on the U2 server even if you are connected to it. You can only edit files on your local machine.

### Settings

Please refer to [Configuration](Configuration.md) to open the configuration file.

Following settings are used for U2 connection.

```
 "db": {
  "host": "",
  "userName": "",
  "password": "",
  "account": "",
  "dataSource": "UNIVERSE",
  "port": 31438
 },
```

- `host`: host name or address of a U2 server.
- `userName`: user name to login to the U2 server.
- `password`: password to login to the U2 server.
- `account`: account name of a U2 server.
- `dataSource`: `UNIVERSE` or `UNIDATA`, by default is `UNIVERSE`.
- `port`: port number of U2 server. For UniVerse and UniData, the port number is `31438` by default.

**Note**: Please enter these settings before connecting to the server.

### Connect to Server

Press <kbd>F1</kbd> to open the command window and then enter the Connect to MV Server command to connect to the server.

If some settings are not set in the configuration file, you will need provide these values when prompted in the command window.

### Disconnect from Server

Press <kbd>F1</kbd> to open the command window and then enter the Disconnect from MV Server command to disconnect to the server.

### Connection status

The connection status icon is displayed in the bottom-left corner.

Click the icon to connect to or disconnect from the U2 server.

![connection_status](../img/connection_status.png)