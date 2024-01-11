## Quick Start

2. **Set Environment Variables**

   Open the `.env` file and set your passwords and other configuration variables:

   - `ELASTIC_PASSWORD`: Password for the 'elastic' user.
   - `KIBANA_PASSWORD`: Password for the 'kibana_system' user.
   - `STACK_VERSION`: Version of the Elastic Stack.
   - `CLUSTER_NAME`: Name of your Elasticsearch cluster.
   - `LICENSE`: Set to 'basic' or 'trial'.
   - `ES_PORT`: Port for the Elasticsearch HTTP API.
   - `KIBANA_PORT`: Port to expose Kibana.
   - `ES_MEM_LIMIT`, `KB_MEM_LIMIT`, `LS_MEM_LIMIT`: Memory limits for each service.
   - `ENCRYPTION_KEY`: Encryption key for secure communication.

3. **Start Docker Compose**

   Initiating Docker Compose will start the Elasticsearch, Kibana, and Logstash services in detached mode, initializing each component according to the defined configuration.

## Configuration Details

### Docker Compose

The `docker-compose.yml` file outlines the setup for Elasticsearch, Kibana, and Logstash:

- **Volumes:** Designated for storing certificates and service data.
- **Networks:** Establishes a default network named `elastic`.
- **Services:** Includes `setup` for initial configuration and individual services for `es01` (Elasticsearch), `kibana`, and `logstash`.

### Elasticsearch Configuration (`es01`)

- Utilizes the specified Elastic Stack version.
- Configures ports, environment variables, and volumes for SSL certificates and data.
- Implements memory limits and health checks.

### Kibana Configuration

- Relies on the Elasticsearch service.
- Arranges environment variables for connection to Elasticsearch, SSL setup, and memory limits.

### Logstash Configuration

- Configured to work in conjunction with Elasticsearch and Kibana services.
- Establishes Logstash with a customized pipeline as defined in `logstash.conf`.
- Sets up SSL certificates and user credentials for secure Elasticsearch communication.

### SSL Certificate Generation

- SSL certificates are generated for secure communication between the services. This is a crucial step for ensuring the security and integrity of data communication within the setup.

## Logstash Pipeline Configuration

The `logstash.conf` file specifies the input, filter, and output settings for Logstash:

- **Input:** Defines how Logstash receives data.
- **Filter:** (Currently empty) Can be used to process and modify the incoming data.
- **Output:** Configures how Logstash sends the processed data to Elasticsearch.

By following these steps and configurations, users can set up a robust Elasticsearch, Kibana, and Logstash environment using Docker, tailored to their specific needs and preferences.
