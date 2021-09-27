Prometheus captures & stores the cluster metrics as a Time Series Data and Grafana uses these metrics for the Dashboard Visulization.
A time series is a data set that tracks a sample over time

A few custom Grafana dashboards are created for the CPU, Memory, Disk and Network Traffic for a Worker Node-1 as shown in the pic "Dashborad Pic" using Kubeadm on Ubuntu.

Instance: In Prometheus terms, an endpoint you can scrape is called an instance, usually corresponding to a single process.
e.g. instance="172.31.82.223:9100"
172.31.82.223: Internal IP of the Node-1
9100: This is the port for Node Exporter to scrap the metrics

Job: A collection of instances with the same purpose, a process replicated for scalability or reliability for example, is called a job.
e.g. job="kubernetes-service-endpoints"
In Prometheus the Node Exporter is using Port:9100 with service type:ClusterIP to scrap metrics for the instances.
