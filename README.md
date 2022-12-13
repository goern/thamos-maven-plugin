# just a quick hack

This Maven plugin is going to count the number of direct/non-transitive dependencies of a project and print the number
to the console.

## Usage

```shell
mvn clean install # to local repository, somewhere in `~/.m2/repository`
mvn dependency:tree # to see the dependencies
mvn thoth:thamos-maven-plugin:0.1.0-SNAPSHOT:dependency-counter # should be 7
```

## Acknowledgements

This follows [How to Create a Maven Plugin][howto].

[howto]: https://www.baeldung.com/maven-plugin
