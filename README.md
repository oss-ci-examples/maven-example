This project demonstrates how to do a  multi-module CI friendly release management with Maven 3.2.1 and above.

Usage: 

```
mvn clean deploy -Drevision=1.0.0
```

The upstream has additional features: tagging/branching. This fork does not use it to keep the example simple.

Inspired by [Maven Release Plugin: Dead and Buried](https://axelfontaine.com/blog/dead-burried.html)
and
[Defining a central version in multi-module projects](https://www.mojohaus.org/flatten-maven-plugin/examples/example-central-version.html)

# Setting up CI builds

This guide uses Travis CI as an example.

## Nightly build

1. Ensure the variables are configured:
 - MVN_DEPLOY_USER
 - MVN_DEPLOY_KEY

2. Deploy with: 

```
mvn clean deploy -s .ci.settings.xml -Drevision=0.2.$TRAVIS_BUILD_NUMBER
```