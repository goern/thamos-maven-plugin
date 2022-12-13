# just a quick hack

This Maven plugin is going to count the number of direct/non-transitive dependencies of a project and print the number
to the console.

## Usage

```shell
mvn clean install # to local repository, somewhere in `~/.m2/repository`
mvn dependency:tree # to see the dependencies
mvn thoth:thamos-maven-plugin:0.1.0-SNAPSHOT:dependency-counter # should be 7
```

it should look something like this:

```shell
[INFO] Scanning for projects...
[INFO]
[INFO] ---------------------< thoth:thamos-maven-plugin >----------------------
[INFO] Building thamos-maven-plugin Maven Plugin 0.1.0-SNAPSHOT
[INFO] ----------------------------[ maven-plugin ]----------------------------
[INFO]
[INFO] --- maven-dependency-plugin:2.8:tree (default-cli) @ thamos-maven-plugin ---
[INFO] thoth:thamos-maven-plugin:maven-plugin:0.1.0-SNAPSHOT
[INFO] +- org.apache.maven:maven-plugin-api:jar:3.8.5:provided
[INFO] |  +- org.apache.maven:maven-model:jar:3.8.5:provided
[INFO] |  +- org.eclipse.sisu:org.eclipse.sisu.plexus:jar:0.3.5:provided
[INFO] |  |  \- javax.annotation:javax.annotation-api:jar:1.2:provided
[INFO] |  +- org.codehaus.plexus:plexus-utils:jar:3.3.0:provided
[INFO] |  \- org.codehaus.plexus:plexus-classworlds:jar:2.6.0:provided
[INFO] +- org.apache.maven:maven-core:jar:3.8.5:provided
[INFO] |  +- org.apache.maven:maven-settings:jar:3.8.5:provided
[INFO] |  +- org.apache.maven:maven-settings-builder:jar:3.8.5:provided
[INFO] |  |  \- org.codehaus.plexus:plexus-sec-dispatcher:jar:2.0:provided
[INFO] |  |     \- org.codehaus.plexus:plexus-cipher:jar:2.0:provided
[INFO] |  +- org.apache.maven:maven-builder-support:jar:3.8.5:provided
[INFO] |  +- org.apache.maven:maven-repository-metadata:jar:3.8.5:provided
[INFO] |  +- org.apache.maven:maven-model-builder:jar:3.8.5:provided
[INFO] |  +- org.apache.maven:maven-resolver-provider:jar:3.8.5:provided
[INFO] |  +- org.apache.maven.resolver:maven-resolver-impl:jar:1.6.3:provided
[INFO] |  +- org.apache.maven.resolver:maven-resolver-api:jar:1.6.3:provided
[INFO] |  +- org.apache.maven.resolver:maven-resolver-spi:jar:1.6.3:provided
[INFO] |  +- org.apache.maven.resolver:maven-resolver-util:jar:1.6.3:provided
[INFO] |  +- org.apache.maven.shared:maven-shared-utils:jar:3.3.4:provided
[INFO] |  +- org.eclipse.sisu:org.eclipse.sisu.inject:jar:0.3.5:provided
[INFO] |  +- com.google.inject:guice:jar:no_aop:4.2.2:provided
[INFO] |  |  +- aopalliance:aopalliance:jar:1.0:provided
[INFO] |  |  \- com.google.guava:guava:jar:25.1-android:provided
[INFO] |  |     +- com.google.code.findbugs:jsr305:jar:3.0.2:provided
[INFO] |  |     +- org.checkerframework:checker-compat-qual:jar:2.0.0:provided
[INFO] |  |     +- com.google.errorprone:error_prone_annotations:jar:2.1.3:provided
[INFO] |  |     +- com.google.j2objc:j2objc-annotations:jar:1.1:provided
[INFO] |  |     \- org.codehaus.mojo:animal-sniffer-annotations:jar:1.14:provided
[INFO] |  +- javax.inject:javax.inject:jar:1:provided
[INFO] |  +- org.codehaus.plexus:plexus-interpolation:jar:1.26:provided
[INFO] |  +- org.codehaus.plexus:plexus-component-annotations:jar:2.1.0:provided
[INFO] |  +- org.apache.commons:commons-lang3:jar:3.8.1:provided
[INFO] |  \- org.slf4j:slf4j-api:jar:1.7.32:provided
[INFO] +- org.apache.maven:maven-artifact:jar:3.8.5:provided
[INFO] +- org.apache.maven:maven-compat:jar:3.8.5:test
[INFO] |  \- org.apache.maven.wagon:wagon-provider-api:jar:3.5.1:test
[INFO] +- org.apache.maven.plugin-tools:maven-plugin-annotations:jar:3.6.0:provided
[INFO] +- junit:junit:jar:4.12:test
[INFO] |  \- org.hamcrest:hamcrest-core:jar:1.3:test
[INFO] \- org.apache.maven.plugin-testing:maven-plugin-testing-harness:jar:3.3.0:test
[INFO]    +- commons-io:commons-io:jar:2.2:provided
[INFO]    \- org.codehaus.plexus:plexus-archiver:jar:2.2:test
[INFO]       +- org.codehaus.plexus:plexus-container-default:jar:1.0-alpha-9-stable-1:test
[INFO]       |  \- classworlds:classworlds:jar:1.1-alpha-2:test
[INFO]       \- org.codehaus.plexus:plexus-io:jar:2.0.4:test
[INFO] ------------------------------------------------------------------------
[INFO] BUILD SUCCESS
[INFO] ------------------------------------------------------------------------
[INFO] Total time:  0.860 s
[INFO] Finished at: 2022-12-13T09:30:36+01:00
[INFO] ------------------------------------------------------------------------
```

and

```bash
[INFO] Scanning for projects...
[INFO]
[INFO] ---------------------< thoth:thamos-maven-plugin >----------------------
[INFO] Building thamos-maven-plugin Maven Plugin 0.1.0-SNAPSHOT
[INFO] ----------------------------[ maven-plugin ]----------------------------
[INFO]
[INFO] --- thamos-maven-plugin:0.1.0-SNAPSHOT:dependency-counter (default-cli) @ thamos-maven-plugin ---
[INFO] Number of dependencies: 7
[INFO] ------------------------------------------------------------------------
[INFO] BUILD SUCCESS
[INFO] ------------------------------------------------------------------------
[INFO] Total time:  0.167 s
[INFO] Finished at: 2022-12-13T09:31:06+01:00
[INFO] ------------------------------------------------------------------------
```

## Acknowledgements

This follows [How to Create a Maven Plugin][howto].

<https://maven.apache.org/guides/introduction/introduction-to-dependency-mechanism.html> is also interesting.

[howto]: https://www.baeldung.com/maven-plugin
