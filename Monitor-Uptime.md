
# How to Set up PagerDuty Alerts in Grafana

In my previous guide [“Monitoring NEAR Node with Prometheus and Grafana”](https://github.com/masknetgoal634/near-prometheus-exporter/blob/master/guide/GUIDE.md), I showed how to set up Prometheus and Grafana and how to send email notifications (Gmail). In this guide, I’d like to share how to set up alert notifications for PagerDuty in Grafana.

## Getting started

PagerDuty is one of the most well-known incident response platforms for IT departments. To set up alerting through PagerDuty, you need to [create an account](https://www.pagerduty.com/sign-up/) there. (PagerDuty is a paid service, but you can always do a 14-day free trial.) Once you’re logged in, go to Configuration -> Services -> + New  Service.

Add a new service:

![](https://raw.githubusercontent.com/masknetgoal634/StakeWarsGuides/master/img/monitor_uptime_new_service.png)

Choose Prometheus from the Integration types list and give the service a name – type a name for example "Grafana". (You can also customize the incident settings, but I went with the default setup.) Then click save.

![](https://raw.githubusercontent.com/masknetgoal634/StakeWarsGuides/master/img/monitor_uptime_intergations.png)

The Integration Key will be displayed. Copy the key.

