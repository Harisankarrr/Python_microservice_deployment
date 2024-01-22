# Python Microservice using Rabbitmq


Microservices Conversation with RabbitMQ




Project Overview
This project showcases an event-driven microservices architecture for a conversation system using RabbitMQ. The two microservices, one built with Django and the other with Flask, communicate asynchronously through RabbitMQ. Additionally, Docker and Docker Compose are utilized for easy deployment and scalability.

Microservices

Django Microservice(admin)

The product application , located admin/ directory, manages products and exposes REST endpoints. It communicates events such as product creation, update, and deletion through RabbitMQ.

Flask Microservice (Main App)

The Flask microservice, located in the main/ directory, serves as the main application. It handles user interactions, likes, and communicates with the Django microservice through RabbitMQ.

RabbitMQ Communication

The Django microservice publishes events such as 'product_created', 'product_updated', and 'product_deleted' to the 'main' exchange in RabbitMQ.
The Flask microservice consumes these events and performs actions accordingly.
## Deployment

To deploy this project run

for the product app (admin project)
# Navigate to the Django microservice directory
cd admin/

# Build the Docker image for the Django microservice
docker-compose build

# Run the Docker containers for the Django microservice
docker-compose up

# Open a new terminal window and navigate to the Django admin
cd admin/

# Apply migrations for the Django microservice
docker-compose exec backend python manage.py migrate




for the main app(admin project)

# Navigate to the Flask microservice directory (Main App)
cd main/

# Build the Docker image for the Flask microservice (Main App)
docker-compose build

# Run the Docker containers for the Flask microservice (Main App)
docker-compose up

# Open a new terminal window and navigate to the Flask microservice (Main App)
cd main/

# Apply any necessary migrations for the Flask microservice (Main App)
# Note: This depends on your specific application requirements
# Example: docker-compose exec backend python manage.py migrate

# If using Flask and SQLAlchemy for database migrations:
docker-compose exec backend flask db upgrade
