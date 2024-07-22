# Monitoring Nginx with Prometheus and Grafana

## Description
This project uses Docker Compose to set up a monitoring environment with Prometheus and Grafana to monitor an Nginx server. Prometheus collects metrics from Nginx, and Grafana visualizes them.

## Getting Started

### Bringing Up the Containers
To start all the containers, run the following command:

```
docker compose up -d
```

### Verify Prometheus
Open your web browser and navigate to http://localhost:9090.
Go to Status > Targets and check that the targets are active and in the "UP" state.

### Modifying the prometheus.yml File

If you want to add more services to monitor, edit the prometheus.yml file (look at the examples).

### Verify Grafana
Open your web browser and navigate to http://localhost:3000.
Log in with the default credentials:
Username: admin
Password: admin
Add Prometheus as a data source:
Go to Configuration > Data Sources > Add data source.
Select Prometheus.
Set the URL to <container-IP>:9090.

________________________________________________________________________________________________________
### Identifying Container IPs

```
docker inspect -f '{{range .NetworkSettings.Networks}}{{.IPAddress}}{{end}}' <container-name>
```


_______________________________________________________________________________________________________
### Accessing Metrics in Grafana
After adding Prometheus as a data source in Grafana, you can create dashboards and visualize the metrics that interest you.

With these steps, you will have your monitoring environment up and running, allowing you to monitor the performance of your Nginx server.
