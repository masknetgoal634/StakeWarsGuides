<img src="https://vitalpoint.ai/wp-content/uploads/2020/06/near_logo-1.png"  width="128" height="33">

---

# How to Set Up DigitalOcean Monitoring Alerts

[DigitalOcean](https://www.digitalocean.com) is a cloud-based infrastructure provider that gives developers a reliable and easy to use virtual servers and object storage. DigitalOcean also offers Network services like load balancers, firewalls, and DNS.  All of these products can be managed through their UI, API, CLI, or client libraries. 

DigitalOcean allows you to set up monitoring of your Droplet and it can send you alerts via email or Slack. After you create a droplet for NEAR node you can monitor inbound and outbound bandwidth, collect metrics and set specific thresholds by percent. The service is integrated into each Droplet in an easy-to-view interface, it’s very useful and free.

## Getting Started

To enable alerts you should [install the metrics agent](https://www.digitalocean.com/docs/monitoring/how-to/install-agent/) on your NEAR node.

Connect to your Droplet via SSH:
```
ssh root@IPADDRESS
````

Install and enable the metrics agent:
```
curl -sSL https://repos.insights.digitalocean.com/install.sh | sudo bash
```

Verify that the agent is running:
```
ps aux | grep do-agent
```

Once the agent is running, enhanced graphs should be available in the control panel.

### Create an Alert Policy

If the metrics agent has been installed correctly you can create a new alert policy. Click the "Create button" in the top menu and select "Alert Policies".

![](https://raw.githubusercontent.com/masknetgoal634/StakeWarsGuides/master/img/send_alerts_create_policy.png)

Select the metric and threshold you want to monitor:

- CPU: The percentage of total CPU used on the Droplet, out of 100%
- Bandwidth — Inbound: The amount of incoming traffic to the Droplet, in MBps
- Bandwidth — Outbound: The amount of outgoing traffic from the Droplet, in MBps
- Disk — Read: The read activity for the Droplet's disks, in MB/s
- Disk — Write: The write activity for the Droplet's disks, in MB/s
- Memory Utilization: The percentage of total memory being used, out of 100%
- Disk Utilization: The percentage of the root disk storage being used, out of 100%

Pick the alert interval, which is how long a Droplet must exceed the threshold before a notification is triggered.

Enter the name of the Droplet to monitor in the Select Dropets or Tags text box.

![](https://raw.githubusercontent.com/masknetgoal634/StakeWarsGuides/master/img/send_alerts_select_droplets.png)

### Select the Alert Notification Method

You should select at least one of the two possible notification methods: email or [Slack](https://slack.com/).
If you wish to receive alerts via Slack, click "Connect Slack" and follow the instructions. 

Enter a label for the alert in the Name and create alert policy text box and click "Create alert policy".

![](https://raw.githubusercontent.com/masknetgoal634/StakeWarsGuides/master/img/send_alerts_alert_policy.png)

When an alert is triggered according to the process outlined above, a notification is sent using the chosen methods.

## What’s Next?

You can use the [DigitalOcean API](https://developers.digitalocean.com/documentation/v2/) to manage(create, resize,...) Droplets and resources within the DigitalOcean cloud in a simple, programmatic way using conventional HTTP requests. 

All of the functionality that you are familiar with in the DigitalOcean control panel is also available through the API, allowing you to script the complex actions that your situation requires.

