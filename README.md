# Single Node Elastic Kibana Logstash (ELK) Setup

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

   Remember to generate the `ENCRYPTION_KEY` using the command `openssl rand -base64 32`.

3. **Start Docker Compose**

   Run the following command in the root directory of this project to start the services:

   ```bash
   docker-compose up -d
   ```
