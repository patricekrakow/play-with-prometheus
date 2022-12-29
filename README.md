# Let's Play with Prometheus!

<https://prometheus.io/docs/introduction/first_steps/>

<https://killercoda.com/playgrounds/scenario/ubuntu>

```text
lscpu
```

<https://prometheus.io/download/>

```text
wget https://github.com/prometheus/prometheus/releases/download/v2.41.0/prometheus-2.41.0.linux-386.tar.gz
```

```text
tar xvfz prometheus-2.41.0.linux-386.tar.gz
```

```text
cd prometheus-2.41.0.linux-386/
```

```text
cat prometheus.yml
```

```text
./prometheus --config.file=prometheus.yml
```

```text
wget https://github.com/prometheus/node_exporter/releases/download/v1.5.0/node_exporter-1.5.0.linux-386.tar.gz
```

```text
tar xvfz node_exporter-1.5.0.linux-386.tar.gz
```

```text
cd node_exporter-1.5.0.linux-386
```

```text
./node_exporter
```

```yaml
global:
  scrape_interval: 15s

scrape_configs:
- job_name: node
  static_configs:
  - targets: ['localhost:9100']
```
