# Sprinter Signing Configuration

This repository stores MPC topology configuration files for the Sprinter signing service. Topology files are automatically uploaded to DigitalOcean Spaces on merge to main.

## Repository Structure

```
/
├── staging/
│   └── topology          # Staging environment topology
├── production/
│   └── topology          # Production environment topology
├── .github/
│   └── workflows/
│       ├── publish-staging.yml
│       └── publish-production.yml
├── README.md
└── CLAUDE.md
```

## Topology Files

Topology files are hex-encoded MPC topology configurations used by the Sprinter signing service.

## Deployment

On merge to `main`, configurations are automatically published to DigitalOcean Spaces:
- `staging/` -> `sprinter-signing-config/staging/`
- `production/` -> `sprinter-signing-config/production/`

