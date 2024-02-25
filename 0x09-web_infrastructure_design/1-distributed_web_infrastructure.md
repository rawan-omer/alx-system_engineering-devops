### Three Server Web Infrastructure Design for www.foobar.com

#### Components:
1. **Load Balancer (HAproxy):**
   - Purpose: Distributes incoming traffic across multiple servers to ensure high availability and scalability.
   - Distribution Algorithm: Round Robin - evenly distributes requests among the available servers.
   - Setup: Active-Passive - one server actively manages traffic while the other remains on standby.
  
2. **Web Server (Nginx):**
   - Purpose: Serves static content efficiently and acts as a reverse proxy to forward requests to the application server.
  
3. **Application Server:**
   - Purpose: Executes the application logic and dynamically generates content based on client requests.
  
4. **Database (MySQL):**
   - Purpose: Stores and manages the website data.
   - Configuration: Primary-Replica (Master-Slave) Cluster.
   - How it Works: The Primary node handles write operations, replicating data changes to the Replica nodes, which serve read requests. This ensures data redundancy and fault tolerance.
   - Difference: The Primary node manages write operations, while Replica nodes primarily handle read operations, reducing the load on the Primary node and enhancing performance.

#### Rationale for Each Component:
- **Load Balancer:** Prevents a single point of failure (SPOF) by distributing traffic among multiple servers.
- **Web Server:** Improves performance by efficiently serving static content and acts as a barrier between clients and the application server, enhancing security.
- **Application Server:** Separates the application logic from the web server, allowing for easier scaling and maintenance.
- **Database:** Provides data storage and redundancy, ensuring data integrity and availability.
#### Issues with the Infrastructure:
1. **Single Point of Failure (SPOF):** 
   - The entire infrastructure is vulnerable to failure if any component fails, particularly if the active load balancer or primary database node goes down.
2. **Security Issues:** 
   - Lack of firewall exposes the servers to potential attacks.
   - Absence of HTTPS encryption exposes sensitive data to interception.
3. **No Monitoring:** 
   - Without monitoring tools, it is challenging to detect and address performance issues, security breaches, or resource constraints proactively.
