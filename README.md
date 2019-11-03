PR1 commit 1

This is an example project that uses the [GitHub Maven Plugins](https://github.com/github/maven-plugins).

See the [POM file](https://github.com/kevinsawicki/github-maven-example/blob/master/example/pom.xml)
for how the downloads plugin and site plugin are configured.

# Getting started

* Fork this project
* Update the `pom.xml` file `<url>` element to be the address of your fork
* Optionally update `<scm>` and `<developers>` section as well to have the information for your fork
* Add the following to your Maven `settings.xml` file updated with your GitHub login name and password:

```xml
<servers>
  <server>
    <id>github</id>
    <username>user</username>
    <password>password</password>
  </server>  
</servers>
```

# Using the downloads plugin

```
$ cd github-maven-example/example
$ mvn clean install
```

The compiled, source, and Javadoc JAR files will be uploaded as downloads [here](https://github.com/kevinsawicki/github-maven-example/downloads).

# Using the site plugin

```
$ cd github-maven-example/example
$ mvn site
```

The generated site will be committed to the [gh-pages branch](https://github.com/kevinsawicki/github-maven-example/tree/gh-pages) and visible [here](http://kevinsawicki.github.com/github-maven-example/).
