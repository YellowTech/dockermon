# dockermon
Very simple monitoring for Docker hosts and containers with [Prometheus](https://prometheus.io/), [Grafana](http://grafana.org/), [cAdvisor](https://github.com/google/cadvisor),
[NodeExporter](https://github.com/prometheus/node_exporter). 


Clone or copy the docker-compose.yml and prometheus.yml to a new folder then create a new folder called 'grafana_db' and replace the user id 1000 from the docker-compose.yml with your own user id.

Create new folder with
```bash
mkdir grafana_db
```
Replace 1000 with your user ID in docker-compose.yml
```bash
sed -i "s/1000/"$(id -u)"/g" docker-compose.yml 
```

Then start the containers using (may need sudo)
```bash
docker-compose up -d
```

and access the grafana web interface over the port 3000. This port can also be given to a reverse proxy to add encryption.
No other ports are opened but the corresponding lines can be uncommented in the docker-compose.yml file


Example dashboards can be found in the Dashboard folder.