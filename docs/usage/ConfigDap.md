
## Configure Debugging Binaries in UniVerse

Please check whether this feature is supported for your U2 server and platform according [this page](./DAPRelease.md).

 - If yes, you need download and configure related binaries.

 - If not, do not change your environment.

To configure the debugging related binaries, please follow below steps.

#### Windows

1. Copy **dap_agent.exe** and **grpcs.exe** from the package to your UniVerse **bin** folder. E.g., *C:\U2\UV\bin*
  
2. Verify whether the unirpcservices file contains **grpcs** service. If **grpcs** service doesn't exist, you must add it manually. Add the new service as shown below to the **unirpcservices** file:

    ```
    grpcs <full_path_to_grpcs.exe> * TCP/IP 0 3600
    ```

    The 'unirpcservices' file can be found in your U2 server installation folder: for example, **C:\U2\unishared\unirpc\unirpcservices**.

#### Linux

1. Copy **dap_agent** and **grpcs** from the package to your UniVerse **bin** folder. For example, */usr/u2/uv/bin/*
  
2. Verify whether the **unirpcservices** file contains the **grpcs** service. If the **grpcs** service doesn't exist, you must add it manually. Add the new service as shown below to the **unirpcservices** file:

    ```
    grpcs <full_path_to_grpcs> * TCP/IP 0 3600
    ```

    The **unirpcservices** file can be found in your U2 server installation folder. For example,  **/usr/u2/unishared/unirpc/unirpcservices**.
