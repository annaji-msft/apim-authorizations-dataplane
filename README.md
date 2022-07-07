# apim-authorizations-dataplane
apim authorizations data plane

Expose API Management Authorizations on Gateway (dataplane). This is helpful when application developers want to use authorizations to enable end user scenarios. 
Comes handy with interactive scenarios esp. Static Web Apps or Mobile Applications.


The repo contains ARM templates to provision the Authorizations API and associated artifacts like policies and named values.

Assuming you have created a API Management Instance
Also create Authorization providers that you would want to use for the application development.

az deployment group create --resource-group apim-rg --template-file swa-easytokens-master.template.json --parameters swa-easytokens-parameters.json --parameters ApimServiceName=test-apim --parameters SubscriptionId=159d7683-f4a0-4b15-8ecc-8542203d3c54 --parameters ResourceGroupId=apim-rg --parameters ServiceId=test-apim --parameters ARMAPIVersion=2021-12-01-preview

Turn on System Assigned Managed Identity for APIM and give it permissions as contributor to the API Management Service. 

After the above command succefully runs you can validate by using the .http file in test folder. This requires rest client vscode extension
