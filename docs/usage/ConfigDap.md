
## Configure Debugging Binaries

Please check whether this feature is supported for your U2 server and platform according [this page](./DAPRelease.md).

 - If yes, you need download and configure related binaries.

 - If not, do not change your environment.

To configure the debugging related binaries, please follow below steps.

## UniVerse

#### Windows

1. Copy **uddap_server** and **uddap_slave** from the package to your UniVerse **bin** folder. E.g., *C:\U2\UV\bin*
  
2. Verify whether the unirpcservices file contains **grpcs** service. If **grpcs** service doesn't exist, you must add it manually. Add the new service as shown below to the **unirpcservices** file:

    ```
    grpcs <full_path_to_grpcs.exe> * TCP/IP 0 3600
    ```

    The 'unirpcservices' file can be found in your U2 server installation folder: for example, **C:\U2\unishared\unirpc\unirpcservices**.

#### Linux

1. Copy **uddap_server** and **uddap_slave** from the package to your UniVerse **bin** folder. For example, */usr/u2/uv/bin/*
  
2. Verify whether the **unirpcservices** file contains the **grpcs** service. If the **grpcs** service doesn't exist, you must add it manually. Add the new service as shown below to the **unirpcservices** file:

    ```
    grpcs <full_path_to_grpcs> * TCP/IP 0 3600
    ```

    The **unirpcservices** file can be found in your U2 server installation folder. For example,  **/usr/u2/unishared/unirpc/unirpcservices**.

## UniData

#### Windows

1. Copy **uddap_server.exe** and **uddap_slave.exe** from the package to your UniData **bin** folder. E.g., *C:\U2\ud83\bin*
  
2. Verify whether the unirpcservices file contains **uddap_server** service. If **uddap_server** service doesn't exist, you must add it manually. Add the new service as shown below to the **unirpcservices** file:

    ```
    uddap_server <full_path_to_uddap_server.exe> * TCP/IP 0 3600
    ```

    The 'unirpcservices' file can be found in your U2 server installation folder: for example, **C:\U2\unishared\unirpc\unirpcservices**.

#### Linux

1. Copy **uddap_server** and **uddap_slave** from the package to your UniData **bin** folder. For example, */usr/u2/ud83/bin/*
  
2. Verify whether the **unirpcservices** file contains the **uddap_server** service. If the **uddap_server** service doesn't exist, you must add it manually. Add the new service as shown below to the **unirpcservices** file:

    ```
    uddap_server <full_path_to_uddap_server> * TCP/IP 0 3600
    ```

    The **unirpcservices** file can be found in your U2 server installation folder. For example,  **/usr/u2/unishared/unirpc/unirpcservices**.