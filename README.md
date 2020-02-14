# Maven CI example

This project demonstrates how to do a multi-module CI publication with Maven 3.2.1 and above:

 - no noisy version bumps in the pom files
 - no tagging/branching (wanted to keep the example simple, upstream repo has this if you need this)
 - published version is clean and semver, i.e. 0.2.1, 0.2.2 (e.g. no timestamp/Git hash in the version)
 - Travis CI publishes a new version on every push to master (see .travis.yml file). See the builds at https://travis-ci.org/oss-ci-examples/maven-example.
 - Travis CI cron job (https://docs.travis-ci.com/user/cron-jobs/#adding-cron-jobs) runs daily and publishes a new version
 - Published artifacts can be found in public JFrog Artifactory: https://linkedin.jfrog.io/linkedin/test-repo/foo/sample/maven/ci/friendly/ci-friendly-parent/ 
 - Unique version is constructed with the help of ```TRAVIS_BUILD_NUMBER``` environment variable.

## Inspiration

- Upstream repo
- [Maven Release Plugin: Dead and Buried](https://axelfontaine.com/blog/dead-burried.html)
- [Defining a central version in multi-module projects](https://www.mojohaus.org/flatten-maven-plugin/examples/example-central-version.html)

## Local testing

1. Point the repo in ```pom.xml``` to your own public repo where you have upload permissions.
2. Export variables with your secrets:
 - MVN_DEPLOY_USER
 - MVN_DEPLOY_KEY
3. Deploy with: 

```
mvn deploy -s .ci.settings.xml -Drevision=0.2.0
```
