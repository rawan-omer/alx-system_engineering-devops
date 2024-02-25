### Description

This web infrastructure is a scaled-up version of the previous one, aimed at enhancing reliability and security. In this version, all Single Points of Failure (SPOFs) have been eliminated, and each major component (web server, application server, and database servers) has been deployed on separate GNU/Linux servers. Additionally, SSL termination is not performed at the load balancer, and each server's network is safeguarded by a firewall, with comprehensive monitoring in place.

### Specifics About This Infrastructure

- **Firewall Protection:**
  - The addition of a firewall between each server ensures enhanced security by preventing unauthorized access and mitigating potential threats. Each server is individually protected, reducing the risk of compromise across the infrastructure.

### Issues With This Infrastructure

- **High Maintenance Costs:**
  - Deploying each major component on its own server increases maintenance costs significantly. The need to purchase additional servers and the subsequent rise in electricity consumption lead to increased operational expenses for the company. Allocating funds for server procurement and electricity bills strains the company's financial resources, impacting its overall budget.
