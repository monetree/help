Steps to create and publish pyhton web app to Azure App service

1. open Azure CLI 
2. Change Powershell to bash command.
3. mkdir <name> -- Make a directory
4. cd name
5. az account list -- Show the account attach to your name 
6. az account set --subscription <subscriptionID>
7. az account show --shows the current subscription which confirms the correct context is set.
8. git clone https://github.com/Azure-Samples/python-docs-hello-world -- clone the repository to your directory.
9. cd python-docs-hello-world
10.az webapp up -n <app-name>
11. Now, Add the URL or web app http://<app-name>.azurewebsites.net to Allowed Host in settings.py file of pyhton web app.
 
 
