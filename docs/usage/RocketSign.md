# RocketSign - Code Signing

RocketSign is Rocket's tool for code signing and verifying the detached signatures. Please follow the steps below:

## Verify Command
   
```bash
openssl dgst -sha256 -verify <public key file> -signature <signature> -binary <file to verify>
```

### Below is detailed information on how to execute the verify command:

1. Extract the **signature file** and **public key** files from the **'rocket-mvbasic-2.9.0_sign.zip'** zip file.
  
2. Unzip the **'rocket-mvbasic-2.9.0_sign.zip'** zip file and execute the commands below for verification:

    ```bash
    openssl dgst -sha256 -verify rocket_mv.pem.pub.key -signature rocket-mvbasic-2.9.0.vsix.sigx -binary rocket-mvbasic-2.9.0.vsix

    Verified OK
    ```

3. Failed use cases:
   
    ```bash
    openssl dgst -sha256 -verify rocket_mv.pem.pub.key -signature rocket-mvbasic-2.9.0.vsix.sigx -binary rocket-mvbasic-2.9.0.vsix

    Verification Failure
    ```