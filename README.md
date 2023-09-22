# Deployment stacks demo

There are two bicep files that can be used here. 

## Deploying the stack

These instructions are operating at the resource group level, but you can have it managed everything at the resource group level, subscription or management group.

The command below deploys the stack out to the subscription. 

```sh
az stack group create --name '<deployment-stack-name>'   --resource-group <resource-group-name> --template-file '<bicep-file-name>' --deny-settings-mode 'none'
```

List all of the stack resources at the resource group scope

```sh
az stack group list --resource-group '<resource-group-name>'
```

[Protecting Resources from deletion](https://learn.microsoft.com/en-us/azure/azure-resource-manager/bicep/deployment-stacks?tabs=azure-cli#protect-managed-resources-against-deletion)

## Updating the stack

Make changes to the bicep file you are managing with stacks and then run the command below. 

```sh
az stack group create --name '<deployment-stack-name>' --resource-group '<resource-group-name>' --template-file '<bicep-file-name>' --deny-settings-mode 'none'
```

## View resources in the deployed stack



## Deleting the stack

The command below deletes all of the resources inside of the resource group. You can also modify the last command to change behavior to --delete-all/--delete-resource-groups if desired. 

```sh
az stack group delete --name '<stack name>' --resource-group '<resource-group>' --delete-resources
```