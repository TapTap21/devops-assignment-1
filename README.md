# DevOps Project 1

## Background
The aim of this project is to create a small application from scratch and apply some good devops principles to the project. The project is about learning and training devops, not about the backend/frontend aspects of it, but they are included as DevOps is by nature a discipline that touches all aspects of development

For the first project we won't focus too much on security.

## Assignment
### Phase 1
1. Create a simple python+flask application that has 4 endpoints:
   1. Healthcheck endpoint: This returns a 200 when the application is healthy
   2. An endpoint to save your name and surname (assume names and surnames are unique)
   3. An endpoint that returns all the names saved
   4. An endpoint to query your surname based on the name you give
2. The application should use postgresql as the backend database.
3. The postgresql database must be run in docker
4. Dockerize the service and add everything to a docker-compose file

### Phase 2
1. Create another, different, flask service that saves names and phone numbers (assume unique)
   1. When a name is queried to the 1st service, that service should communicate with this service to get the associated phone number of a name.
   2. Communication between services should happen with a broker based system. I suggest using rabbitmq.
   3. Add an endpoint to also save phone numbers in this service
2. The rabbitmq broker should be deployed in docker
3. Add everything to the docker-compose. The 2 python services should be 2 separate containers running.

### Phase 3
1. Add Grafana and Prometheus to the docker-compose and get them talking.
2. Use prometheus to monitor you healthcheck endpoints
3. Install prometheus-flask-exporter to get specific flask based metrics
4. Monitor rabbitmq with prometheus
5. Make some cool dashboards in grafana to visualize all this.
6. Add some basic info logging to you apps ("added JOHN DOE to the database")
7. Add [loki](https://grafana.com/oss/loki/) to you docker-compose
8. You promtail to scrape the logs from you services and write them to loki
9. View the logs in grafana and add them to the dashboard
10. Use promtail to scrape rabbitmq logs and add them to the dashboard

### Phase 4
1. Use github-actions to automatically build and push your container images to a container-registry (dockerhub, ghcr, etc.)
2. Write a basic unit test for the services using any framework you like
3. Run the unit tests in the CI in a place that makes sense. If the tests fail, the containers should NOT push.

### Phase 5 
1. Create an AWS account
2. Using free-tier, create a EC2 server and ssh key that goes with it
3. Using github-actions, deploy the docker-compose to the EC2 server

## FAQ
If you have any questions, feel free to contact me at wernich.bekker@gmail.com or create an issue on the repo.