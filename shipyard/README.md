# Docker file of Shipyard

## Usage

### Install

```bash
curl -sSL https://shipyard-project.com/deploy | ACTION=deploy IMAGE=shipyard/shipyard:master bash -s
```

### Upgrade

```bash
curl -sSL https://shipyard-project.com/deploy | ACTION=upgrade IMAGE=shipyard/shipyard:master bash -s
```

### Remove

```
curl -sSL https://shipyard-project.com/deploy | ACTION=remove bash -s
