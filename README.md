# Open-SaaS
This is a repository for my own SaaS deployement by using open source projects. The Service itself is pretty simiar than the well known GCC or AWS Services, however its much more simple. The general assumtion is that the mid sized companies, majors offices, small-sized companies do not have the necessary resources to medernize their infrastrcture, or to start building up their own. Very often these companies cannot see the benefit of investing into their infrastructure and perform even simple workflows in a Cloud environment like: Documentations, Publishing documents, Sign documents by their own system in a digital format, store data in centralized databased instead of using excel all the time, defining document templates and many more. Obviously they are also not using services such as ERP system, to entirely manage their HR processes, HR Database, Production data, Production Workflows, Delivery processes & Workflows, and most importantly Accountant activities like payout process, monitoring their cashflow and many other actvities are not covered, and taken care manually by somebody in the company, burning effort unnecesary week by week.
In the upcoming chapters, I describe the necessary Eco-System to deploy Open Source Solutions for customers easily, build up new Docker Containers providing the service to the customers, and also most importantly how scaling up such a business can lead into massivly collaborate to Open- Source repositories and creating a totally new revenue stream by contributing to big Developer Communities.


# What to offer for people
1. PostgreSQL with custom user interface --> Additional Service: Integrate databases with their customers
2. ERTNext
3. Odoo ERP
4. Grafana (With / without PostgreSQL or Prometheus) --> Additional Service: Define Dashboard with KPIs based on consultations
5. On Prem Github
6. HomeAssistance
7. Wordpress (With deployement of info provided by customer, maybe also template)
8. NodeJS Website with limited features (Which backend? Its still a question)
9. Metabase
10. OpenSign (Odoo Also have signing feature)
11. Documentation Solution
12. Guacamole RDP (Remote Desktop Gateway)

# Environment Setup
On each Server PC the following ecosystem is requred on the Native Linux Ecosystem:
- Webadmin: Monitor the Server performance on a WebUI: Easy setup of firewall, Networking, Hardware, Clusters, System Administration
- NGinX Proxy Manager: Deploy the services run in Docker Containers to dimaons / sub-domains.
- Docker + Portainer.io (Every Service runs in Docker containers from custom build images. Portainer.io is a pretty nice WebUI to monitor each Docker containers, and have a full control over the Images, Networks and their volums)
- Jenkins
- Grafana

# How the Server works?
The Server is responsible to deploy each demo system, what the customers can see. Also, the Server is able tu run all the services what customers can request via the web interface, such as deploying a customized demo for trial.
So the following Services shall be covered (I have already tried to describe couple of workflows, also provided a draft design):
-- Setup a new instance of one fo the Open Source Systems. In this example lets say it is an Odoo ERP.
1. Jenkins checks out the latest Odoo ERP from out fork\Odoo Master, and checks whether a latest image is available
2. If the image is not available, we build it.
3. We generate a Docker Compose file based on a template, which is saved into our own Github reposititory.
4. Once the Docker Compose files are ready, we make sure that the Service can run on the Server / Slave machine without any problem.
5. We configure a new DNS Record and map the sub-domain to the Server / Slave address.
6. If the Service is stable, we configure the NgiX Server via cli, and map it to the user/given_demo_name, so make the service available on a subdomain.
7. Jenkins makes sure that the Service runs on the subdomain, by a REST call. Based on the header info, we conclude that the service is up and running.
8. We trigger a build to shut down the Service in 30days.


# How the Slaves are configured?

# Marketing the Service

# Business model
