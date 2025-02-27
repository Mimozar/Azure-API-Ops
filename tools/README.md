# Debug Instructions using Visual Studio Code Dev Container
This option allows you to run the extractor and publisher binaries on your local machine inside a container. Thus you won't need to install any SDKs on your local machine.

## Required Tools
* Make sure you have [Visual Studio Code](https://code.visualstudio.com/download) installed.
* Make sure you have the [VS Code Dev Container extension](https://marketplace.visualstudio.com/items?itemName=ms-vscode-remote.remote-containers) installed.
* Make sure you have [Docker Desktop](https://www.docker.com/products/docker-desktop/) installed. 

## Debugging in Dev Container
* Log in to Azure from a bash or zsh terminal via: `az login --use-device-code`
* Generate deployment credentials:  
  ```bash
  az ad sp create-for-rbac --name myApp --role contributor --scopes /subscriptions/{subscription-id}/resourceGroups/exampleRG --sdk-auth
  ```
* The output is a JSON object with the role assignment credentials. Copy this JSON object for later. You'll only need the sections with the clientId, clientSecret, subscriptionId, and tenantId values.
* Update the values in the `.env.extractor` file to include the information required for the extractor to run sucessfully.
* Update the values in the `.env.publisher` file to include the information required for the publisher to run sucessfully
* Place a breakpoint on the opened source code file
* Run the "Launch Extractor" from the debugger section in VS Code to debug the extractor
* Run the "Launch Publisher" from the debugger section in VS Code to debug the publisher

# Debug Instructions using Github Codespaces
This option allows you to run the extractor and publisher binaries in a container where you can spin up fully configured dev environments in the cloud that start in seconds.

## Creating new Github Codespaces Instance

* To learn more about Codespaces, go to [GitHub Codespaces Documentation - GitHub Docs](https://docs.github.com/en/codespaces).
* In your github repository:
  * Click the `Code` button on this repo
    * Select `Codespaces` tab, next to `Local`
    * Click `New codespace`

## Debugging in Github Codespaces

* Log in to Azure from a bash or zsh terminal via: `az login --use-device-code`
* Generate deployment credentials:  
  ```bash
  az ad sp create-for-rbac --name myApp --role contributor --scopes /subscriptions/{subscription-id}/resourceGroups/exampleRG --sdk-auth
  ```
* The output is a JSON object with the role assignment credentials. Copy this JSON object for later. You'll only need the sections with the clientId, clientSecret, subscriptionId, and tenantId values.
* Update the values in the `.env.extractor` file to include the information required for the extractor to run sucessfully.
* Update the values in the `.env.publisher` file to include the information required for the publisher to run sucessfully
* Place a breakpoint on the opened source code file
* Run the "Launch Extractor" from the debugger section in VS Code (remember that Github Codespaces runs VS Code in the browser) to debug the extractor
* Run the "Launch Publisher" from the debugger section in VS Code (remember that Github Codespaces runs VS Code in the browser) to debug the publisher

