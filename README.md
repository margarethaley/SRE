# Site Reliability Engineering (SRE)

## What is SRE?

Site Reliability Engineering, or SRE, is a software engineering approach to manage operations for systems, applications, and services. We use software as a tool to manage systems, solve problems, and automate operations tasks.

If you are interested in learning SRE practices, you're in the right place! This page provides an overview of the SRE principles and guidelines for managing the [Operate  First](https://operate-first.github.io/operate-first/) services.

## Services Monitored

We have [Open Data Hub](https://opendatahub.io/) applications deployed and running in an MOC [(Mass Open Cloud)](https://massopen.cloud/) cluster. Open Data Hub is an end-to-end AI/ML platform on top of OpenShift Container Platform which provides various tools for Data Scientists and Engineers.

The components we currently have available are:
* [JupyterHub](https://jupyterhub-opf-jupyterhub.apps.zero.massopen.cloud/hub/login)

## SLI and SLOs

For each of the Operate First managed services, we define Service Level Indicators (SLI) and Service Level Objectives (SLO). SLIs help us monitor the availability of the service, and SLOs define goals for us to improve its reliability.

The `sli-slo` folder [here](https://github.com/operate-first/SRE/tree/master/sli-slo) lists out the SLI/SLO for each of the applications in separate markdown files. For eg, you can find the SLI/SLO defined for the `JupyterHub` application [here](https://github.com/operate-first/SRE/blob/master/sli-slo/jupyterhub.md).

## Operational Tools

* [Prometheus](http://prometheus-portal-opf-monitoring.apps.zero.massopen.cloud/graph) - Monitoring tool capturing time series metrics for available Operate First services
* [Prometheus Alertmanager](https://prometheus.io/docs/alerting/latest/alertmanager/) - Alertmanager for handling alerts and routing them to the appropriate receiver integration such as Email, Slack, PagerDuty etc
* [Grafana](https://grafana-route-opf-monitoring.apps.zero.massopen.cloud/) - Visualization tool for creating monitoring dashboards
* [GitHub Receiver](https://github.com/m-lab/alertmanager-github-receiver) - Incident reporting tool for handling outages/incidents

## Incident Management

All of the Operate First services are monitored by Prometheus. We use Prometheus metrics to identify and define alerts on possible outages/incidents.

The [GitHub Alertmanager Receiver](https://github.com/m-lab/alertmanager-github-receiver) is our chosen tool for handling and reporting outages/incidents to our users.

The [`incident-management`](https://github.com/operate-first/SRE/tree/master/incident-management) folder contains more information on how to setup GitHub alertmanager receiver and configure Prometheus alerts.

## Runbooks

For each of the services being monitored, we define runbooks for providing information on how to administer, debug, and effectively troubleshoot common problems of a service.

We will place runbooks in the [`runbooks`](https://github.com/operate-first/SRE/tree/master/runbooks) folder.
