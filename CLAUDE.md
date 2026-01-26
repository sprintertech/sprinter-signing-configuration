# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Repository Purpose

This repository stores MPC topology configuration files for the Sprinter signing service. Configurations are uploaded to DigitalOcean Spaces for use by Sprinter services.

## Repository Structure

- `staging/` - Staging environment configurations
  - `topology` - MPC topology file (hex-encoded)
- `production/` - Production environment configurations
  - `topology` - MPC topology file (hex-encoded)

## Topology File Format

Topology files are hex-encoded strings containing MPC topology configuration. These are not JSON files - they are raw hex data used by the signing service.

## Deployment

On merge to `main`, configurations are automatically published to DigitalOcean Spaces (`sprinter-signing-config` bucket):
- `staging/` -> `sprinter-signing-config/staging/`
- `production/` -> `sprinter-signing-config/production/`

GitHub Actions workflows use secrets `DO_SPACES_KEY` and `DO_SPACES_SECRET` for authentication.

## Working with Configurations

When modifying topology files:
1. Ensure the file contains valid hex-encoded data
2. Test changes in staging before promoting to production
3. Topology files should not have a file extension
