# GaraSign - Code Signing

GaraSign is Rocket's new tool for code signing and verifying the detached signatures. Please follow the steps below:

## Verify Command
   
```bash
openssl dgst -verify <public key file> -signature <signature> <file to verify>
```

### Below is detailed information on how to execute the verify command:

1. Extract the **signature file** and **public key** files from the **'rocket-mvbasic-2.5.1_sign.zip'** zip file.
  
2. Unzip the **'rocket-mvbasic-2.5.1_sign.zip'** zip file and execute the commands below for verification:

    ```bash
    openssl dgst -verify rocket_mv.pem.pub.key -signature rocket-mvbasic-2.5.1.vsix.sig rocket-mvbasic-2.5.1.vsix

    Verified OK
    ```

    ```bash
    openssl dgst -verify rocket_mv.pem.pub.key -signature uvdap-uv1421-linux.tar.gz.sig uvdap-uv1421-linux.tar.gz

    Verified OK
    ```

    ```bash
    openssl dgst -verify rocket_mv.pem.pub.key -signature uvdap-uv1421-windows.zip.sig uvdap-uv1421-windows.zip

    Verified OK
    ```

3. Failed use cases:
   
    ```bash
    openssl dgst -verify rocket_mv.pem.pub.key -signature rocket-mvbasic-2.5.1.vsix.sig rocket-mvbasic-2.5.1.vsix

    Verification Failure
    ```