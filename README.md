### Build the image:

    docker build -t rabbitmq https://github.com/denibertovic/rabbitmq-dockerfile.git

### Running the container:

    docker run -p :5672 -p :15672 rabbitmq
    
### Persisting data:

    mkdir -p /tmp/rabbitmq/mnesia
    chmod 777 /tmp/rabbitmq/mnesia
    docker run -h rabbithost -p :5672 -p :15672 -v /tmp/rabbitmq/mnesia:/var/lib/rabbitmq/mnesia rabbitmq
    # settings the hostname is required because Rabbitmq uses the $HOSTNAME variable in its data