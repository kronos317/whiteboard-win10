========================================================

## 2021-01-06

How to install RabbitMQ offline module

### Install Erlang + Dependencies

In **erlang+dependencies** folder, we have 3 rpm files.

=== 1. Install Erlang package

```
# sudo rpm -Uvh ./erlang-23.2.1-1.el7.x86_64.rpm
```

This is zero-dependency erlang RPM, which is available in this [github page](https://github.com/rabbitmq/erlang-rpm)

=== 2. Install socat & logrotate package

```
# sudo rpm -Uvh ./socat-1.7.3.2-2.el7.x86_64.rpm

# sudo rpm -Uvh ./logrotate-3.8.6-19.el7.x86_64.rpm
```

These files are downloaded by using **yum-plugin-downloadonly**.

### Install RabbitMQ

In **rabbitmq** folder, we have 1 rpm file and 1 key file.

=== 1. Add signing key

```
# sudo rpm --import ./rabbitmq-signing-key-public.asc
```

=== 2. Install rabbitmq-server

```
# sudo rpm -Uvh ./rabbitmq-server-3.8.8-1.el6.noarch.rpm
```

### Disable Firewall & SELinux

=== 1. Disable Firewall

```
# sudo systemctl disable firewalld
# sudo systemctl stop firewalld
```

=== 2. Disable SELinux

```
# sudo vi /etc/selinux/config

SELINUX=disabled
```

Restart is required.

### Start RabbitMQ server

=== 1. Start server

```
# sudo systemctl start rabbitmq-server
```

=== 2. Automatically start server at boot time

```
# sudo systemctl enable rabbitmq-server
```

### RabbitMQ Config (Optional, Not tested)

Create rabbitmq conf file at `/etc/rabbitmq/rabbitmq.conf`

```
listeners.ssl.default = 5671

ssl_options.cacertfile = /path/to/cacertfile.pem
ssl_options.certfile   = /path/to/certfile.pem
ssl_options.keyfile    = /path/to/keyfile.pem
ssl_options.verify     = verify_peer
ssl_options.versions.1 = tlsv1.2
ssl_options.versions.2 = tlsv1.1
ssl_options.fail_if_no_peer_cert = false

tcp_listen_options.backlog       = 128
tcp_listen_options.nodelay       = true
tcp_listen_options.exit_on_close = false
tcp_listen_options.keepalive     = false

heartbeat = 580
```

### RabbitMQ Web Management Console

=== 1. Enable RabbitMQ web management console

```
# sudo rabbitmq-plugins enable rabbitmq_management
```

=== 2. Modify file permissions

```
# sudo chown -R rabbitmq:rabbitmq /var/lib/rabbitmq/
```

=== 3. Create an admin user (Change password to a strong password)

```
# sudo rabbitmqctl add_user admin password
```

=== 4. Make admin user and administrator

```
# sudo rabbitmqctl set_user_tags admin administrator
```

=== 5. Set admin user permissions

```
# sudo rabbitmqctl set_permissions -p / admin ".*" ".*" ".*"
```

=== 6. To access the RabbitMQ admin

`http://localhost:15672`

For further information, please check [this](https://gist.github.com/fernandoaleman/fe34e83781f222dfd8533b36a52dddcc)
