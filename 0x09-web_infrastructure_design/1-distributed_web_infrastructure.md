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
   - Purpose: Stores and manages the website's data.
   - Configuration: Primary-Replica (Master-Slave) Cluster.
   - How it Works: The Primary node handles write operations, replicating data changes to the Replica nodes, which serve read requests. This ensures data redundancy and fault tolerance.
   - Difference: The Primary node manages write operations, while Replica nodes primarily handle read operations, reducing the load on the Primary node and enhancing performance.

#### Rationale for Each Component:
- **Load Balancer:** Prevents a single point of failure (SPOF) by distributing traffic among multiple servers.
- **Web Server:** Improves performance by efficiently serving static content and acts as a barrier between clients and the application server, enhancing security.
- **Application Server:** Separates the application logic from the web server, allowing for easier scaling and maintenance.
- **Database:** Provides data storage and redundancy, ensuring data integrity and availability.
```md
### Three Server Web Infrastructure Design for www.foobar.com

#### Components:
1. **Load Balancer (HAproxy):**
   - Purpose: Distributes incoming traffic across multiple servers to ensure high availability and scalability.
