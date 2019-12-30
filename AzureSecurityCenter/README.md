# Sample Azure Security Center blueprint template

This blueprint template provides you Azure Blueprint artifact to deploy Azure Security Center. 

Before deploying this blueprint you need to install [Az.Blueprint module](https://powershellgallery.com/packages/Az.Blueprint/)

To deploy the blueprint, run the following script:

```powershell
$bluePrintName = "azsec_blueprint"
$subscriptionId = "YOUR_SUBSCRIPTION"

Import-AzBlueprintWithArtifact -Name $bluePrintName `
                               -SubscriptionId $subscriptionId `
                               -InputPath .\AzureSecurityCenter\
```

> Note: you must put Azure Security Center template in **artifacts** folder.
