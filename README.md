# RabbitMQ

RabbitMQ is an open-source message broker that facilitates the secure and efficient transmission of messages. It is widely used in distributed systems and microservices architectures to enable asynchronous communication between components.

## Key Features of RabbitMQ:
1. **Message Queuing**: Messages are held in a queue until the recipients are ready to process them.
2. **Asynchronous Communication**: System components can communicate without being directly connected, making the system more flexible and scalable.
3. **Load Balancing**: Messages can be distributed to multiple consumers for load balancing.
4. **Support for Various Protocols**: Works with different protocols such as AMQP (Advanced Message Queuing Protocol).
5. **High Reliability**: Offers various mechanisms to ensure messages are not lost (e.g., making messages persistent).

## Use Cases:
- **Microservices**: Enables communication between different services.
- **Real-Time Applications**: Used in systems requiring real-time data streams, such as games and chat applications.
- **Data Processing**: Helps manage data flow in big data processing.

RabbitMQ assists developers in building more robust and sustainable system architectures.

RabbitMQ offers numerous features that make it a powerful messaging broker, with advanced settings and configurations. Here are some advanced settings and features:

### 1. **Exchange Types**
RabbitMQ provides message routing capabilities with different types of exchanges:
- **Direct Exchange**: Routes messages to specific queues based on a routing key.
- **Fanout Exchange**: Broadcasts messages to all bound queues.
- **Topic Exchange**: Routes messages based on a pattern; sent to queues that match a specific pattern.
- **Headers Exchange**: Routes messages based on header attributes.

### 2. **Queue Management**
- **Queue Properties**: You can configure attributes such as durability, auto-deletion, and prefetch settings.
  - `durable`: Determines whether the queue is persistent.
  - `exclusive`: Ensures the queue is only used by the connection that created it.
  - `auto-delete`: Automatically deletes the queue when there are no more consumers.

### 3. **Message Properties**
- **Message Durability**: Ensures messages are persistent before being written to the queue (using the `deliveryMode` setting).
- **TTL (Time-To-Live)**: Automatically deletes messages that are not consumed within a specified time frame.
- **Priority**: Allows assigning priority to messages, enabling higher priority messages to be processed faster.

### 4. **Security**
- **User Authorization**: Configure user access permissions for specific resources.
- **TLS/SSL Support**: Enhances security by encrypting data transmission.
- **LDAP and OAuth2 Integration**: Centralizes user authentication through a managed system.

### 5. **Load Balancing and Distribution**
- **High Availability (HA) Queues**: Replicates messages across multiple nodes.
- **Shovel and Federation**: Facilitates message transfer between different RabbitMQ servers.

### 6. **Performance Enhancements**
- **Prefetch Count**: Sets the maximum number of messages that consumers can take, balancing the processing load.
- **Batching**: Processes messages in batches, which can improve performance.
- **Asynchronous Message Processing**: Speeds up the system by reducing message processing times.

### 7. **Monitoring and Management**
- **RabbitMQ Management Plugin**: Provides a web-based interface to view information about queues, exchanges, and consumers.
- **Prometheus and Grafana Integration**: Used for monitoring system performance.

### 8. **Policies**
- **Queue Policies**: Define behaviors of queues for special cases (TTL, max-length, etc.).
- **Exchange Policies**: Similar settings applied to exchanges.

### 9. **Dead Letter Exchange (DLX)**
- Allows messages that cannot be processed for certain reasons (e.g., TTL expiration or consumer rejection) to be routed to another queue.

### 10. **Message Routing**
- **Binding**: Manages the relationships between queues and exchanges.

## To run the project:

1. Build the project.
```
mvn clean package
```
2. Using Docker Compose.
```
docker-compose up --build
```
3. Sending Messages
```
curl -X POST http://localhost:8080/send -d "Hello RabbitMQ!"
```
