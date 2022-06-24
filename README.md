# RabbitMQ-Tutorial

RabbitMQ is a message broker: it accepts and forwards messages. A message broker acts as a middleware which which provide an asynchronous way of communication between services. They can be used to reduce loads and delivery times of web application servers.

The basic architecture of a message queue is simple - there are two kinds of applications interacting with a messaging system: producers and consumers.
- ***Producers*** are those, who sends messages to a broker 
- ***Consumers***, who receive messages from the broker.

Messages placed onto the queue are stored until the consumer retrieves them.
![image](https://user-images.githubusercontent.com/82801063/175519231-58a4612d-9a96-460a-83e5-4fc1ed152056.png)

The two applications will only communicate through the messages they are sending to each other, which means the Producer and Consumer have low coupling.\
A ***Queue*** act as a message storage buffer where messages are stored until they are consumed by the consumer. Messages are always added to the end of the Queue. This Queue is located within the Broker. A message is the data transported between the Publisher and the Consumer. Essentially, messages are byte arrays with some headers added on top.\
Messages are actually not published directly to a Queue. Instead, the producer sends messages through an **Exchange**.\
### Exchange
An **exchange** is responsible for routing the messages to different queues with the help of bindings and routing keys.\
A **binding** is a link between a queue and an exchange.\
The **Routing Key** is mainly what the Exchange looks for when deciding how to route the message to queues.\
#### Types of Exchange -
- **Direct** - The message is routed to the queues whose binding key exactly matches the routing key of the message.
- **Topic** - Messages are routed to one or many queues based on a matching between a message routing key and the routing pattern specified by the queue binding.
- **Fanout** - A fanout exchange copies and routes a received message to all queues that are bound to it regardless of routing keys or pattern matching as with direct and topic exchanges. The keys provided will simply be ignored.
- **Header** - Headers exchanges are very similar to topic exchanges, but route messages based on header values instead of routing keys. A message matches if the value of the header equals the value specified upon binding.

A **Connection** is made between your service and the AMQP broker. One Connection can have multiple channels.\
A **Channel** is a virtual connection inside that connection. All messages within the system are always sent through a channel.\
