# Quickstart

This is a guide to help you get up and running with the solution for the Azure IoT Operations (AIO).

For more detailed information on the deployment of AIO core components follow this [doc](./provisioning/PROVISIONING.ipynb).

## Usage

1. Run the deploy script from `infra` directory.

```bash
   ./deploy.sh
```

> **Note**: If required, reset your environment using the [00-clean-up.sh](./provisioning/00-clean-up.sh) script, which will delete the k3d cluster and then recreate the cluster with the right image and settings.

### [OPTIONAL] Individual Steps

You can also walk through and explore using the Jupyter Notebooks created for this solution. To get started, take a look at the [provisioning notebook](./provisioning/PROVISIONING.ipynb).

## Troubleshooting and debugging

Please see [troubleshooting](../docs/TROUBLESHOOTING.md) documents that can help you to navigate through troubleshooting.