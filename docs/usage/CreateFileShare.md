# Create a File Share on U2 server

You can create a File Share of your U2 server to use on your development environment.

## Share U2 Folder on Windows

Ask your system administrator to create a file share on your Windows U2 server. They can follow this process:

2. Open **Windows Explorer** on the U2 server.
3. Browse to the U2 folder, e.g., `C:\U2\`.
4. Right-click the `UV` or `Udt` folder and click **Properties**.
5. Select the **Sharing** tab.
6. Click **Share**.  
The **Network Access** window opens.
7. Click **Share** and wait for the process to finish.  
The **Your folder is shared message** will show.
8. Click **Done**.  
This displays the network path needed to map the file share as a network drive.

## Share U2 Directory on Linux

Ask your system administrator to create a SAMBA share of the U2 parent folder, e.g., `/usr/uv/`.

1. Load samba.
2. 
3. 

## Map a Share to a Network Drive

To connect to your U2 server shared folder:

1. Open Windows Explorer.
2. Click on **This PC**. 
3. Click on **Map network drive** in the **Computer** tab.  
The **Map Network Drive** window opens.
4. Select a **Drive:** letter.  
You can choose U: for U2 server.
5. In **Folder:** paste the network path as noted above.
6. Select **Reconnect at sign-in**.
7. When required, select to **Connect using different credentials**.  
8. Click **Finish**.  
You might be prompted with the **Enter Network Credentials** window.