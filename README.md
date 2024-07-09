# ATM Payment Processing Application

This Spring Boot application demonstrates ATM payment processing using Kafka for event-driven communication.

## Modules and Components

### Controllers

1. **DepositProducer.java**
    - Endpoint: `/api/atm/deposit`
    - Sends a `DepositEvent` to Kafka when a deposit is made to an account.

2. **WithdrawalProducer.java**
    - Endpoint: `/api/atm/withdraw`
    - Sends a `WithdrawalEvent` to Kafka when a withdrawal is made from an account.

### Services

1. **AccountService.java**
    - Manages account details and performs balance updates based on deposit and withdrawal events.

### Kafka Streams Processor

1. **KafkaStreamsProcessor.java**
    - Configures Kafka Streams to process deposit and withdrawal events, updating account balances and sending `DatabaseChangeEvent` to another Kafka topic.

### Kafka Configuration

1. **KafkaProducerConfig.java**
    - Configures Kafka producers for `DepositEvent`, `WithdrawalEvent`, and `DatabaseChangeEvent`.

## Configuration

- **Kafka Broker**: Ensure the Kafka broker URL is configured correctly via environment variables or `application.properties`.

- **Topics**:
    - `kafka.topic.deposit`: Topic for deposit events.
    - `kafka.topic.withdrawal`: Topic for withdrawal events.
    - `kafka.topic.database-change`: Topic for database change events.

## Running the Application

### Prerequisites

- JDK 8 or higher
- Maven 3.x
- Docker (if running Kafka locally in containers)


