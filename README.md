# streadway/amqp Conneciton/Channel auto reconnect wrap
streadway/amqp Connection/Channel does not reconnect if rabbitmq server restart/down.

To simply developers, here is auto reconnect wrap with detail comments.

## How to change existing code
1. add import `import "github.com/sirius1024/go-amqp-reconnect/rabbitmq"`
2. Replace `amqp.Connection`/`amqp.Channel` with `rabbitmq.Connection`/`rabbitmq.Channel`!

## Example
### Close by developer
> go run example/close/demo.go

### Auto reconnect
> go run example/reconnect/demo.go

### RabbitMQ Cluster with Reconnect
```go
import "github.com/sirius1024/go-amqp-reconnect/rabbitmq"

rabbitmq.DialCluster([]string{"amqp://usr:pwd@127.0.0.1:5672/vhost","amqp://usr:pwd@127.0.0.1:5673/vhost","amqp://usr:pwd@127.0.0.1:5674/vhost"})
```
