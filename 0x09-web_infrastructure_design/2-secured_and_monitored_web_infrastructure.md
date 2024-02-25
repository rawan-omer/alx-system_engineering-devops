### Description

This GitHub repository contains the design and documentation for a three-server web infrastructure hosting the website www.foobar.com. The infrastructure is designed to prioritize security, scalability, and monitoring. It incorporates three firewalls, an SSL certificate for encrypted traffic, and monitoring clients for real-time performance tracking.

### Specifics About This Infrastructure

- **Firewalls for Enhanced Security:**
  - Three firewalls are included to control and monitor incoming and outgoing network traffic. Firewalls act as a barrier between the servers and external networks, filtering traffic based on predefined rules to prevent unauthorized access and potential security threats.

- **SSL Certificate for Secure Communication:**
  - An SSL certificate is implemented to serve www.foobar.com over HTTPS, ensuring that all data transmitted between the server and client is encrypted. HTTPS protects sensitive information from interception and tampering, enhancing the security and privacy of user interactions with the website.

- **Monitoring for Performance and Stability:**
  - Three monitoring clients, such as Sumo Logic or similar tools, are deployed to collect and analyze data from the servers. Monitoring allows administrators to track key metrics, identify performance issues, and ensure the infrastructure operates optimally. 

### Monitoring Data Collection Process

- The monitoring tool continuously collects data from the servers, including system metrics, application logs, and network traffic.
- Data is aggregated and analyzed in real-time to detect anomalies, trends, and potential issues.
- Alerts are generated based on predefined thresholds or deviations from normal behavior, enabling prompt response to performance degradation or security incidents.

### Monitoring Web Server QPS (Queries Per Second)

To monitor web server QPS:

1. Configure the monitoring tool to collect HTTP request metrics, including the number of queries received per second.
2. Create dashboards or reports to visualize QPS trends over time, facilitating performance analysis and capacity planning.
3. Set up threshold alerts to notify administrators of significant deviations from expected QPS levels, indicating potential traffic spikes or abnormalities.

### Issues With This Infrastructure

- **Terminating SSL at the Load Balancer Level:**
  - Terminating SSL at the load balancer exposes decrypted traffic within the internal network, potentially compromising data security. Implementing end-to-end encryption ensures data remains encrypted throughout transmission, reducing the risk of unauthorized access or data breaches.

- **Single MySQL Server for Writes:**
  - Relying on a single MySQL server for write operations creates a single point of failure and may lead to data inconsistency or loss in the event of server failure. Implementing database replication or clustering enhances fault tolerance and ensures data availability.

- **Uniformity of Server Components:**
  - Deploying servers with identical components increases vulnerability to widespread failures, such as software vulnerabilities or hardware defects. Diversifying server configurations and components reduces the impact of potential failures and enhances overall system resilience and reliability.
