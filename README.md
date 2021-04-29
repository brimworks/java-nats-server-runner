![NATS](src/main/javadoc/images/large-logo.png)

# Java Nats Server Runner

Run the Nats Server from your Java code. 

A [Java](http://java.com) client for the [NATS messaging system](https://nats.io).

[![License Apache 2](https://img.shields.io/badge/License-Apache2-blue.svg)](https://www.apache.org/licenses/LICENSE-2.0)
[![Maven Central](https://maven-badges.herokuapp.com/maven-central/io.nats/jnats-server-runner/badge.svg)](https://maven-badges.herokuapp.com/maven-central/io.nats/jnats-server-runner)
[![Javadoc](http://javadoc.io/badge/io.nats/jnats-server-runner.svg?branch=main)](http://javadoc.io/doc/io.nats/jnats-server-runner?branch=main)
[![Release Badge](https://github.com/nats-io/java-nats-server-runner/actions/workflows/build.yml/badge.svg?event=push)](https://github.com/nats-io/java-nats-server-runner/actions/workflows/build.yml)

Useful for running unit or integration tests on the localhost.

By default, the server must be in your path under the name `nats-server`
or you must set the `nats_server_path` environment variable.

```java
try (NatsServerRunner server = new NatsServerRunner()) {
    System.out.println("Server running on port: " + server.getPort())

    Connection c = Nats.connect(server.getURI());
    
    ...
}
```
