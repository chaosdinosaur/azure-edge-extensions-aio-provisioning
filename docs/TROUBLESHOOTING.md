# Troubleshooting Guide

This guide provides solutions for common issues you may encounter.

## Problem 1: Custom Location OID cannot be retrieved

### Symptom for Problem 1

When running `az connectedk8s enable-features -n $CLUSTER_NAME -g $RESOURCE_GROUP --custom-locations-oid $ARC_CUSTOMLOCATION_OID --features cluster-connect custom-locations`, you may receive the following:

"WARNING: Unable to fetch the Object ID of the Azure AD application used by Azure Arc service. Unable to enable the 'custom-locations' feature. Insufficient privileges to complete the operation."

"Unable to fetch the Object ID of the Azure AD application used by Azure Arc service. Proceeding with the Object ID provided to enable the 'custom-locations' feature."

### Cause for Problem 1

Most likely the cause is when using service principal.

When using service principal, as we do in Github Actions workflow, the Object ID for custom locations feature is not retrievable when running `az connectedk8s enable-features`. This will then use the parameter --custom-locations-oid, and therefore needs to be correct.

When using user account, you will not get the same issue as it is able to retrieve the oid, when running `az connectedk8s enable-features`. 

### Solution for Problem 1

To resolve this issue for Service Principal in GitHub Actions follow the steps described [here](https://learn.microsoft.com/en-us/azure/azure-arc/kubernetes/custom-locations#enable-custom-locations-on-your-cluster).

Follow steps:

1. Login to your user account
1. Retrieve OID with the command

   ```bash
        # Azure CLI version lower than 2.37.0
        az ad sp show --id bc313c14-388c-4e7d-a58e-70017303ee3b --query objectId -o tsv

        # Azure CLI version 2.37.0 or higher
        az ad sp show --id bc313c14-388c-4e7d-a58e-70017303ee3b --query id -o tsv
    ```

1. Save that as Github Secret for your Github Actions
1. Pass it as a value for the parameter --custom-locations-oid for the below command in your pipeline.

    ```bash
        az connectedk8s enable-features -n $CLUSTER_NAME -g $RESOURCE_GROUP --custom-locations-oid $ARC_CUSTOMLOCATION_OID --features cluster-connect custom-locations
    ```