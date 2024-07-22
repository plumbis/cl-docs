---
title: What's New
author: NVIDIA
weight: 20
product: NVIDIA Air
---
<!-- vale off -->
Check out the latest updates to {{<exlink url="https://air.nvidia.com" text="NVIDIA Air">}}.

## July 2024
<!-- Air:WhatsNew -->
### 82.2024.0722-014
- Added `generic/ubuntu2404` image with support for `cloud-init`
- Updated `generic/ubuntu2204` and `generic/ubuntu2004` images with support for `cloud-init`
<!-- Air:WhatsNew -->

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