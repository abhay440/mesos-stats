# Mesos Stats

Scripts to collect mesos cluster stats.

## main.py

Usage:

```shell
shell> ./main.py <MASTER_HOST> <GRAPHITE_HOST> <GRAPHITE_PREFIX> [<SLEEP_SECONDS=60>]
```

Where:
- `<MASTER>` is the host of any mesos master in the cluster.
- `<GRAPHITE_HOST>` is the host for your carbon instance, e.g. `carbon.host.com`
- `<GRAPHITE_PREFIX>` is a prefix for the stats, e.g. `mesos.production.eu`
- `<SLEEP_SECONDS>` is the number of seconds to sleep between gathering date (default 60)

## To build and run in a docker container

```shell
docker build --rm --tag mesos-stats .
docker run -d -e MESOS_MASTER_HOST=<MESOS_MASTER_HOST> -e CARBON_HOST=<CARBON_HOST> -e GRAPHITE_PREFIX=<GRAPHITE_PREFIX> -e PERIOD_SECONDS=<SLEEP_SECONDS> mesos-stats
```