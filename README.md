# RabbitMQ-Tutorial

RabbitMQ is a message broker: it accepts and forwards messages. A message broker acts as a middleware which which provide an asynchronous way of communication between services. They can be used to reduce loads and delivery times of web application servers.

The basic architecture of a message queue is simple - there are two kinds of applications interacting with a messaging system: producers and consumers. Producers are those, who sends messages to a broker, and consumers, who receive messages from the broker. Messages placed onto the queue are stored until the consumer retrieves them.
![image](https://user-images.githubusercontent.com/82801063/175519231-58a4612d-9a96-460a-83e5-4fc1ed152056.png)
