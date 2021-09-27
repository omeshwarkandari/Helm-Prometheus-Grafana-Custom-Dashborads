Prometheus captures & stores the metirics over a database on the back end known as a time series database. Simply put, this database is optimized to store and retrieve data organized as values over a period of time while Grafana uses this database for dataa visulization known as Grafana Dashboards.

How Prometheus Work?
The first thing Prometheus needs is a target. Targets are the endpoints that supply the metrics that Prometheus stores. These endpoints can be the actual endpoint being monitored, or they can be a piece of middleware known as an exporter. Endpoints can be supplied via a static configuration or they can be "found" through a process called service discovery. 
Once Prometheus has a list of endpoints, it can begin to retrieve metrics from them. Prometheus retrieves metrics in a very straightforward manner; a simple HTTP request. 

Importance of Exporter: Prometheus can only use HTTP to talk to endpoints for metrics collection and it can face challenges if an end point e.g. Switch/Router which listens into SNMP rather than HTTP requests. Here comes the Exporter small, purpose-built programs designed to stand between Prometheus and anything you want to monitor that doesn't natively support Prometheus. 

A few custom Grafana dashboards are created for the CPU, Memory, Disk and Network Traffic for a Worker Node-1 as shown in the pic "Dashborad Pic" using Kubeadm on Ubuntu.

Instance: In Prometheus terms, an endpoint you can scrape is called an instance, usually corresponding to a single process.
e.g. instance="172.31.82.223:9100"
172.31.82.223: Internal IP of the Node-1
9100: This is the port for Node Exporter to scrap the metrics

Job: A collection of instances with the same purpose, a process replicated for scalability or reliability for example, is called a job.
e.g. job="kubernetes-service-endpoints"
In Prometheus the Node Exporter is using Port:9100 with service type:ClusterIP to scrap metrics for the instances.
