# Running Locally

## Bicep Infra Deployment

### Generating an SSH Key
This repository contains a Bicep deployment that creates Linux virtual machines, which require an SSH public key. 
This README provides instructions on how to generate an SSH key, and how to use it in your Bicep deployment.

1. **Open PowerShell or Command Prompt**:
    - Press `Win + X` and select "Windows PowerShell" or "Command Prompt".

2. **Generate the SSH Key**:
    - Run the following commands:
      ```sh
      cd [your git repo root]
      ssh-keygen -t rsa -b 4096 -C "admin@contoso.com" -f key
      ```

Additional hints:
- The private key is only needed if you decide to ssh into the machines created by this deployment. 
- You only need to do this if you want to run the Bicep templates locally. This step is handled in the github workflow for pipeline deployments. 
- Do not check these files in to your repository (they are in .gitignore)
- Ensure the _public_ key ('key.pub') is in the correct place. It should be in the repository root, where it is referenced by the Bicep deployment in [`containers.bicep`](infra/bicep/resources/containers.bicep#L107).


### Deploying Bicep
Use the Azure CLI to deploy your Bicep template. Ensure you are in the directory containing your 'main' Bicep file and run:
 ```shell
 az deployment sub create --location <location> --name <unique-name> --template-file main.bicep 
 ```

### Troubleshooting

- **Invalid Path**: If you encounter an error related to the path, double-check that the relative path to your public key is correct.
- **Permission Denied**: Ensure you have the necessary permissions to read the public key file.

