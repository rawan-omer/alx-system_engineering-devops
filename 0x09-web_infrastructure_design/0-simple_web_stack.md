### Whiteboard Design: One Server Web Infrastructure for www.foobar.com

#### Components:
- **Server**: Hosted at IP 8.8.8.8
- **Web Server (Nginx)**: Serves static content and forwards dynamic requests to the application server.
- **Application Server**: Executes application logic and generates dynamic content based on user requests.
- **Application Files**: Contains the code base of the website.
- **Database (MySQL)**: Stores and manages website data.

#### Infrastructure Explanation:

**User Accessing the Website:**
- The user types www.foobar.com into their web browser.
- The domain name www.foobar.com is resolved to the server's IP address 8.8.8.8 through DNS.

**Specifics About This Infrastructure:**
- **Server**: Acts as a physical or virtual machine responsible for hosting the web infrastructure components.
- **Domain Name**: Maps human-readable domain names (like www.foobar.com) to IP addresses, allowing users to access websites using memorable names.
- **DNS Record for www**: The www record in www.foobar.com is a CNAME (Canonical Name) record, which points to the domain's root record.
- **Web Server (Nginx)**: Handles incoming HTTP requests, serves static files directly, and passes dynamic requests to the application server for processing.
- **Application Server**: Executes application-specific logic, interacts with the database, and generates dynamic content based on user requests.
- **Database**: Stores website data, such as user accounts, posts, and other dynamic content.
- **Server Communication with User's Computer**: Utilizes the HTTP protocol to communicate with the user's computer, exchanging requests and responses over the internet.

**Issues With This Infrastructure:**
- **Single Point of Failure (SPOF)**: The entire website relies on a single server, leading to downtime if the server experiences hardware failure or becomes unavailable.
- **Downtime During Maintenance**: Performing maintenance tasks, such as deploying new code or updating software, requires restarting the web server, resulting in temporary downtime.
- **Scalability Limitations**: Inability to handle large volumes of incoming traffic effectively, leading to performance issues or website unavailability during peak periods.

