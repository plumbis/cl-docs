---
title: What's New
author: NVIDIA
weight: 20
product: NVIDIA Air
---
<!-- vale off -->
Check out the latest updates to {{<exlink url="https://air.nvidia.com" text="NVIDIA Air">}}.

## September 2024
<!-- Air:WhatsNew -->
### 82.2024.0926-014
- Allow a ZTP script to be added to any simulation at time of creation
- Updated the topology API to allow retrieval of a topology based on the simulation ID
- Fixed an issue where the organization dropdown was not rendered properly
- Fixed an issue when creating a simulation using JSON containing an invalid interface name
- Fixed an issue when importing JSON with a link for an undefined node
- Fixed an issue when importing JSON containing a `network_pci` configuration
- Fixed an issue where interfaces could be assigned an invalid MAC address when using the topology API
<!-- Air:WhatsNew -->

### 82.2024.0919-011
- Fixed a pagination issue when viewing organization members
- Fixed an issue when sorting members of an organization
- Fixed an issue when adding multiple members to an organization
- Fixed an issue where tokens could be created with an expiration date in the past
- Fixed the SSH link content in the services list
- Streamlined the node deletion confirmation
- Updated the simulation edit dialog
- Added an API endpoint supporting JSON import for simulations
- Added a search field to the nodes and links tabs in the simulation workspace
- Added a tooltip to display the full node name in the simulation workspace
- Added layout options for the topology in the simulation workspace
- Added an actions column to the nodes list
- Added a running node count under the organization details
- Added the ability to manage user permissions for a simulation

## August 2024
### 82.2024.0826-011
- Updated ZTP script template

### 82.2024.0819-011
- Fixed an issue where the `Enable SSH` option was not displayed after deleting the service
- Fixed an issue with pop-out consoles in the Legacy UI

### 82.2024.0815-011
- New UI now available for all users

### 82.2024.0801-011
- Changed simulation title requirements

## July 2024
### 82.2024.0722-014
- Added `generic/ubuntu2404` image with support for `cloud-init`
- Updated `generic/ubuntu2204` and `generic/ubuntu2004` images with support for `cloud-init`

## June 2024
### 82.2024.0627-013
- Updated the template ZTP script

### 82.2024.0613-012
- Fixed an issue where specifying an image by name in a dot file could cause an error

## May 2024
### 82.2024.0523-014
- Added `cumulus-vx-5.9.1` to the OS dropdown of the builder
- Updated the Swagger API view

### 82.2024.0516-013
- Fixed an issue when waking up large simulations

### 82.2024.0513-013
- Fixed an issue where some content types were rejected in API requests
- Improved dot file parsing performance for larger topologies

## April 2024
### 82.2024.0418-011
- Fixed an issue where node rebuild was improperly handled when a worker was offline

## March 2024
### 82.2024.0321-013
- Increased the number of retries when the Air Agent connects to the API
- Fixed an issue when deleting an organization with existing simulations

### 82.2024.0314-013
- Fixed an issue where MAC addresses were not properly validated
- Fixed an issue where node hostnames were allowed to contain whitespace
- Fixed an issue where attempting to create a simulation could improperly return a 400
- Fixed an issue that caused invalid links to be created during DOT file parsing
- Fixed an issue that prevented updating a shared topology after a simulation was deleted

## February 2024
### 82.2024.0229-012
- Fixed an issue that would cause the console not to render for a device
- Updated the default NetQ URL

### 82.2024.0222-010
- Added an API endpoint to automatically generate an out-of-band network

### 82.2024.0215-013
- Fixed an issue where the simulation API did not return all jobs for a loading simulation
- Fixed an issue where the login API incorrectly returned a 500 error

### 82.2024.0206-010
- Signing up for a new account now requires a valid business email address

## January 2024
<!-- Air:WhatsNew -->
### 82.2024.0104-012
- Updated font used by configuration migration tool
<!-- Air:WhatsNew -->
<!-- vale on -->
{{< /expand >}}