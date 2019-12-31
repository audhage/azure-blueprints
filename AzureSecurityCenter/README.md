# Sample Azure Security Center blueprint template

This blueprint template provides you Azure Blueprint artifact to deploy Azure Security Center. 

Before deploying this blueprint you need to install [Az.Blueprint module](https://powershellgallery.com/packages/Az.Blueprint/)

# Import and Publish

```powershell
$bluePrintName = "azsec_blueprint"
$subscriptionId = "YOUR_SUBSCRIPTION"

Import-AzBlueprintWithArtifact -Name $bluePrintName `
                               -SubscriptionId $subscriptionId `
                               -InputPath .\AzureSecurityCenter\
```

> Note: you must put Azure Security Center template in **artifacts** folder.

```powershell
$bluePrintName = "azsec_blueprint"
$subscriptionId = "YOUR_SUBSCRIPTION"
$version = "1.0"
$ascBlueprint = Get-AzBlueprint -Name $bluePrintName `
                                -SubscriptionId $subscriptionId
Publish-AzBlueprint -Blueprint $ascBlueprint `
```
# Assignment

```powershell
$blueprintAssignmentName = "azsec_asc_assignment"
$subscriptionId = "YOUR_SUBSCRIPTION"
$assignmentFilePath = ".\AzureSecurityCenter\assign.json"
 
$ascBlueprint = Get-AzBlueprint -Name $bluePrintName `
                                -SubscriptionId $subscriptionId
                                
New-AzBlueprintAssignment -Name $blueprintAssignmentName ` 
                          -Blueprint $ascBlueprint `
                          -SubscriptionId $ $subscriptionId `
                          -AssignmentFile $assignmentFilePath `
                          -Verbose
```


