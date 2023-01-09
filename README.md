# Let's Play with Prometheus!

## Linux

<https://killercoda.com/playgrounds/scenario/ubuntu>

```text
sudo apt update
```

```text
sudo apt upgrade -y
```

```text
uname --all
```

## Prometheus

<https://prometheus.io/download/>

```text
VERSION=2.37.5; echo $VERSION
```

```text
OS=linux; echo $OS
```

```text
ARCH=386; echo $ARCH
```

```text
wget https://github.com/prometheus/prometheus/releases/download/v$VERSION/prometheus-$VERSION.$OS-$ARCH.tar.gz
```

```text
tar xvfz prometheus-$VERSION.$OS-$ARCH.tar.gz
```

```text
cd prometheus-$VERSION.$OS-$ARCH/
```

```text
cat prometheus.yml
```

```text
./prometheus --config.file=prometheus.yml
```

```text
http://localhost:9090/
```

```text
promhttp_metric_handler_requests_total
```

## Node Exporter

```text
VERSION=1.5.0; echo $VERSION
```

```text
OS=linux; echo $OS
```

```text
ARCH=386; echo $ARCH
```

```text
wget https://github.com/prometheus/node_exporter/releases/download/v$VERSION/node_exporter-$VERSION.$OS-$ARCH.tar.gz
```

```text
tar xvfz node_exporter-$VERSION.$OS-$ARCH.tar.gz
```

```text
cd node_exporter-$VERSION.$OS-$ARCH/
```

```text
./node_exporter
```

### Configure Prometheus

```text
cd prometheus-2.37.5.linux-386/
```

```text
nano prometheus.yml
```

```yaml
scrape_configs:
  - job_name: node
    static_configs:
      - targets: ['localhost:9100']
```

```text
node_cpu_seconds_total
```

## Grafana

<https://grafana.com/grafana/download>

```text
wget https://dl.grafana.com/oss/release/grafana-9.3.2.linux-amd64.tar.gz
```

```text
tar -zxvf grafana-9.3.2.linux-amd64.tar.gz
```

```text
cd grafana-9.3.2/
```

```text
./bin/grafana-server web
```

```text
http://localhost:3000
```

## References

<https://prometheus.io/docs/introduction/first_steps/>

<https://prometheus.io/docs/guides/node-exporter/>

<https://prometheus.io/docs/visualization/grafana/>

<https://grafana.com/docs/grafana/latest/setup-grafana/installation/debian/>

<https://grafana.com/docs/grafana/latest/getting-started/build-first-dashboard/>

<https://linuxhint.com/install-prometheus-raspberry-pi/>
