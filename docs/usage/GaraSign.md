# GaraSign - Code Signing

GaraSign is Rocket's new tool for code signing and verifying the detached signatures. Please follow the steps below:

## Verify Command
   
```bash
openssl dgst -verify <public key file> -signature <signature> <file to verify>
```

### Below is detailed information on how to execute the verify command:

1. Extract the **signature file** and **public key** files from the **'rocket-mvbasic-2.5.0-garasign.zip'** zip file.
  
2. Unzip the **'rocket-mvbasic-2.5.0-garasign.zip'** zip file and execute the command below for verification:

    ```bash
    openssl dgst -verify rocket_mv.pem.pub.key -signature rocket-mvbasic-2.5.0.vsix.sig rocket-mvbasic-2.5.0.vsix

    Verified OK
    ```

3. Failed use cases:
   
    ```bash
    openssl dgst -verify rocket_mv.pem.pub.key -signature rocket-mvbasic-2.5.0.vsix.sig rocket-mvbasic-2.5.0.vsix

    Verification Failure
    ```