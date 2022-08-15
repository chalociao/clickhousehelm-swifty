# clickhousehelm-swifty

The chart contains following resource configuration:
- 1 Deployment of clickhouse client
- 3 services, one each for client, cluster ip for clickhouse and cluster ip for zookeeper
- 1 config map for clickouse config
- 1 stateful set for to persist zookeeper data

The 2 users, writer and reader are defined in configd.yaml under users.xml section. You need to provide passwords for these users first in values.yaml file at lines 8 and 9.

I've kept the replica count as 2 for now, you may switch it later in values.yaml file.
## Installation

```bash
helm install -f ./clickhouse/values.yaml clickhouse --namespace=default ./clickhouse
```

## Docker image build
```bash
docker build -t clickhouse-server ./clickhouse/docker
```

## Uninstallation

```bash
helm uninstall clickhouse
```
