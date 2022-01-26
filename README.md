# vigilant-rotary-phone
export RESOURCE_GROUP=[sandbox resource group name]
export AZURE_REGION=centralus
export AZURE_APP_PLAN=popupappplan-$RANDOM
export AZURE_WEB_APP=popupwebapp-$RANDOM
az group list --output table
az group list --query "[?name == '$RESOURCE_GROUP']"
az appservice plan create --name $AZURE_APP_PLAN --resource-group $RESOURCE_GROUP --location $AZURE_REGION --sku FREE
az appservice plan list --output table
Kind    Location    MaximumNumberOfWorkers    Name                NumberOfSites    ResourceGroup                               Status
------  ----------  ------------------------  ------------------  ---------------  ------------------------------------------  --------
app     Central US  3                         popupappplan-54321  0                Learn-12345678-1234-1234-1234-123456789abc  Ready
