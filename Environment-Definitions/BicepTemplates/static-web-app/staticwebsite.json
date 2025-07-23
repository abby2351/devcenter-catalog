{
    "$schema": "https://schema.management.azure.com/schemas/2019-04-01/deploymentTemplate.json#",
    "contentVersion": "1.0.0.0",
    "parameters": {
        "staticSites_drse_name": {
            "defaultValue": "drse",
            "type": "String"
        }
    },
    "variables": {},
    "resources": [
        {
            "type": "Microsoft.Web/staticSites",
            "apiVersion": "2024-11-01",
            "name": "[parameters('staticSites_drse_name')]",
            "location": "East US 2",
            "tags": {
                "ministry": "health",
                "servicenow": "chg2673",
                "Application": "application",
                "DateCreated": "01/23/2025",
                "Environment": "prod"
            },
            "sku": {
                "name": "Free",
                "tier": "Free"
            },
            "properties": {
                "stagingEnvironmentPolicy": "Enabled",
                "allowConfigFileUpdates": true,
                "provider": "None",
                "enterpriseGradeCdnStatus": "Disabled"
            }
        },
        {
            "type": "Microsoft.Web/staticSites/basicAuth",
            "apiVersion": "2024-11-01",
            "name": "[concat(parameters('staticSites_drse_name'), '/default')]",
            "location": "East US 2",
            "dependsOn": [
                "[resourceId('Microsoft.Web/staticSites', parameters('staticSites_drse_name'))]"
            ],
            "properties": {
                "applicableEnvironmentsMode": "SpecifiedEnvironments"
            }
        }
    ]
}
