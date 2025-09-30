# Sensor_Cassandra_PySpark
## Setting up repository
1. Install Docker and Docker Compose
2. Clone the repository
3. Navigate to the project directory

## Setting up Cassandra and Jupyter with PySpark
1. Docker compose file
2. docker compose up -d
3. docker exec -it cassandra cqlsh -e 'create keyspace sensor_data with replication = {'class': 'SimpleStrategy', 'replication_factor': 1};
4. docker exec -it cassandra cqlsh -e 'create table sensor_data.sensor_readings (sensor_id text, timestamp timestamp, temperature float, humidity float, PRIMARY KEY (sensor_id, timestamp)) WITH CLUSTERING ORDER BY (timestamp DESC);'
5. cd ~/Sensor_Cassandra_PySpark
    mkdir -p notebooks
    sudo chown -R 1000:1000 notebooks
6. docker logs jupyter-spark
7. Open browser and go to localhost:8888
8. Create a new notebook and select PySpark
9. Run the code in the notebook

## Running:
1. docker compose up -d
2. Open browser and go to localhost:8888

## Stopping:
1. just turn off