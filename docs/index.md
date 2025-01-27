# Welcome to ZephCast

ZephCast is a powerful and flexible messaging library that provides a unified interface for working with multiple message brokers. It currently supports Kafka, RabbitMQ, and Redis, offering both synchronous and asynchronous clients.

## Key Features

### Multiple Broker Support
- **Apache Kafka**: Industry-standard distributed streaming platform
- **RabbitMQ**: Feature-rich message broker supporting multiple messaging patterns
- **Redis Streams**: Lightweight, in-memory data structure store

### Developer-Friendly
- **Unified Interface**: Consistent API across all message brokers
- **Async Support**: Native async/await support for all clients
- **Type Safety**: Full type hints support
- **Error Handling**: Robust error handling and recovery mechanisms

### Advanced Features
- **Consumer Groups**: Support for consumer groups in Kafka and RabbitMQ
- **Exchange Bindings**: Advanced RabbitMQ exchange and queue bindings
- **Stream Processing**: Redis Streams support for stream processing

## Quick Example

```python
from zephcast.kafka.async_client import AsyncKafkaClient

async def kafka_example():
    # Create a client
    client = AsyncKafkaClient(
        stream_name="my-topic",
        bootstrap_servers="localhost:9092"
    )
    
    # Connect
    await client.connect()
    
    # Send messages
    await client.send("Hello Kafka!")
    
    # Receive messages
    async for message in client.receive():
        print(f"Received: {message}")
        break
    
    # Close connection
    await client.close()
```

## Getting Started

Check out our [Quick Start Guide](getting-started/quickstart.md) to begin using ZephCast in your project.

## Why ZephCast?

### Unified Interface
ZephCast provides a consistent interface across different message brokers, making it easy to switch between them or use multiple brokers in the same application.

### Type Safety
Built with type hints from the ground up, ZephCast helps catch errors early and provides excellent IDE support.

### Async First
Designed for modern async/await Python, ZephCast makes it easy to build high-performance messaging applications.

### Production Ready
Thoroughly tested and used in production, ZephCast includes robust error handling and recovery mechanisms.

## Support

- [GitHub Issues](https://github.com/zbytealchemy/zephcast/issues)
- [Documentation](https://zephcast.readthedocs.io/en/latest/)
- [Contributing Guide](development/contributing.md)
