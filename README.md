# clickhousehelm-swifty

The chart contains following resource configuration:
- 1 Deployment of clickhouse client
- 3 services, one each for client, cluster ip for clickhouse and cluster ip for zookeeper
- 1 config map for clickouse config
- 1 stateful set for to persist zookeeper data

I've kept the replica count as 2 for now, you may switch it later in values.yaml file.
## Installation

```bash
helm install -f ./clickhouse/values.yaml clickhouse --namespace=default ./clickhouse
```
## Uninstallation

```bash
helm uninstall clickhouse
```
