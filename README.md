# Azure IoT Operations Jumpstart

This repository provides a comprehensive provisioning of Azure IoT Operations. 

## Getting Started

### Prerequisites

1. A running GitHub Codespace of this repository.
1. Dev container setup with k3d cluster. Upon creation of the Codespace, a k3d cluster "devcluster" is already running and ready to use.
1. **Azure Subscription**: `az login` has been executed and default subscription has been set. Ensure you have access to an Azure subscription where you can deploy resources.

### Quickstart
In order to explore the solution, you can use the GitHub Codespace to quickly setup the environment and deploy the Azure IoT Operations components.

> [!IMPORTANT]
> Codespaces are easy to setup quickly and tear down later, but they're not suitable for performance evaluation or scale testing. For those scenarios, use a validated environment from the official documentation.
>
> Azure IoT Operations is currently in preview and not recommended for production use no matter the environment.

1. Use this GitHub codespace to explore Azure IoT Operations in your browser without installing anything on your local machine.

   [![Open in GitHub Codespaces](https://github.com/codespaces/badge.svg)](https://codespaces.new/Azure-Samples/azure-edge-extensions-aio-dp-jumpstart?quickstart=1)

1. Follow the instructions available in the [Quickstart README.md](./infra/README.md). This will setup the infrastructure with an Arc-enabled K3d cluster and Azure IoT Operations components.

## Resources
- [Azure IoT Operations Preview](https://learn.microsoft.com/en-us/azure/iot-operations/)