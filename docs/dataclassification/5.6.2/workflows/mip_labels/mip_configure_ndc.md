# MIP Labels Configuration

Netwrix Data Classification for Files and Folders supports MIP labels as Workflow action. Perform
the following steps to enable MIP labels:

1. In administrative web console, navigate to System →Config . In the tree view go to System → MIP
   Configuration.
2. Complete the MIP Configuration wizard. Review the following mapping table:

    | Netwrix Data Classification | Microsoft Azure Application parameters (fields)                                                                                                                                                        |
    | --------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
    | Client ID                   | Application (client) ID                                                                                                                                                                                |
    | Application Name            | Display name                                                                                                                                                                                           |
    | Tenant                      | Directory (tenant) ID                                                                                                                                                                                  |
    | Certificate Thumbprint      | Provide certificate thumbprint you copied and stored on this step: [Upload the .CER file to Azure](/docs/dataclassification/5.6.2/workflows/mip_labels/mip_configure_infrastructure.md). |

**NOTE:** Any labels and policies in API should be migrated / synced with O365 Security &
Compliance. Review the following Microsoft article for more information:
[To migrate Azure Information Protection labels](https://docs.microsoft.com/en-us/azure/information-protection/configure-policy-migrate-labels#to-migrate-azure-information-protection-labels)
