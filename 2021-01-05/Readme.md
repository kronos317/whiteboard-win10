========================================================

## 2021-01-06

How to install RabbitMQ offline module

### Install Erlang + Dependencies

In **erlang+dependencies** folder, we have 3 rpm files.

=== 1. Install Erlang package

```
# rpm -Uvh ./erlang-23.2.1-1.el7.x86_64.rpm
```

This is zero-dependency erlang RPM, which is available in this [github page](https://github.com/rabbitmq/erlang-rpm)

=== 2. Install socat & logrotate package

```
# rpm -Uvh ./socat-1.7.3.2-2.el7.x86_64.rpm

# rpm -Uvh ./logrotate-3.8.6-19.el7.x86_64.rpm
```

These files are downloaded by using **yum-plugin-downloadonly**.

### Install Erlang + Dependencies
