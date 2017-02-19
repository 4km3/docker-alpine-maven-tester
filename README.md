# maven-tester
Perform acceptance tests in a previously built Java jar

## Building
```console
$ docker build -t 4km3/maven-tester .
```
## Configuration
### Default values
```text

: "${RELEASE_JAR?Need Java app to test}" 
: "${GITHUB_REPO?Need a repository name}" 
: "${GITHUB_USER?Need a GitHub username}" 
: "${GITHUB_BRANCH:=master}" 
: "${REPO_DIR:=.}" 
: "${MAVEN_ACCEPTANCE_TEST_TARGET:=test}" 
```
### Recommended values
By passing these values when running:
```text
RELEASE_JAR=<Java application JAR file URL>
GITHUB_REPO=<Repository name containing the Maven project>
GITHUB_USER=<GitHub user> 
```
you will meet the minimum requirements. Also you might need to modify some of the other default values.

## Running
```console
$ docker run                                                                     \
    --rm                                                                         \
    -e RELEASE_JAR=$RELEASE_JAR                                                  \
    -e GITHUB_REPO=$GITHUB_REPO                                                  \
    -e GITHUB_USER=$GITHUB_USER                                                  \
    -e GITHUB_BRANCH=$GITHUB_BRANCH                                              \
    -e REPO_DIR=$REPO_DIR                                                        \
    -e MAVEN_ACCEPTANCE_TEST_TARGET=$MAVEN_ACCEPTANCE_TEST_TARGET                \
    4km3/maven-tester
```
Also a runme script is provided for convenience

## Authors
pancho horrillo <pancho@pancho.name>

Rodrigo de la Fuente <rodrigo@delafuente.email>

## Acknowledgements
Thanks to Raúl Sánchez @rawmind0 for his invaluable guidance!
