This project demonstrates how to do a  multi-module CI friendly release management with Maven 3.2.1 and above.

Usage: 

~~~~
mvn clean deploy -Drevision=0.2.$BUILD_NUMBER
~~~~

The upstream also has tagging/branching. This fork does not use it.

Inspired by [Maven Release Plugin: Dead and Buried](https://axelfontaine.com/blog/dead-burried.html)
and
[Defining a central version in multi-module projects](https://www.mojohaus.org/flatten-maven-plugin/examples/example-central-version.html)