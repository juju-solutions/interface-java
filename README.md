# Overview

This interface layer handles the communication with Java related services via the
`java-interface` interface protocol.  It will set one state when appropriate:

  * `{relation_name}.ready` indicates that Java is available

In addition, the charm providing this relation (e.g., [openjdk-jre][])
will install a JRE and Java libraries, and will configure the environment in
`/etc/environment`.


# Example Usage

An example of a charm using this interface would be:

TODO: make this more better.  talk provides and requires

```python
@when('java.connected')
def install():
    jre.install()

@when('java.connected')
def java_ready(java):
    jre.configure()
    status_set('active', 'OpenJDK JRE is ready')
```


# Contact Information

- <bigdata@lists.ubuntu.com>


# OpenJDK

- [OpenJDK](http://openjdk.java.net/) home page


[openjdk-jre]: https://jujucharms.com/apache-hadoop-plugin/
