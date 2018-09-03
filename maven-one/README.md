# Maven Tutorial 101

This simple app is an introduction to Maven

## Getting Started
### Prerequisites

You most have an understanding of how to install software on your computer. If you do not know to do this, ask for help.

### Installation

First find your maven version:

```
mvn --version
```
It should print out your installed version of Maven

### Creating a project from command prompt

```
mvn archetype:generate -DgroupId=com.mavenone.sample -DartifactId=maven-one -DarchetypeArtifactId=maven-archetype-quicstart -DinteractiveMode=false
```
This is the Maven goal *archetype:generate*, and passed in various parameters to that goal. 
The prefix *archetype* is the **plugin** and the *generate* is the **goal**.
In conclusion a *plugin* is a collection of *goals* with a general common purpose.  

## Running Maven Tools
### Maven Phases
A phase is a step in the **build lifecycle**, which is an ordered sequence of phases. 
When a phase is given, Maven will execute every phase in the seuqence up to and includeing the one defined. 
This is a list of the most common *default* lifecycle phases executed:
* **validate**: validate the project is correct and all necessary information is available.
* **compile**: compile the source code of the project
* **test**: test the compiled source code using a suitable unit testing framework. These tests should not require the code be packaged or deployed.
* **package**:  take the compiled code and package it in its distributable format, such as a JAR.
* **integration-test**:  process and deploy the package if necessary into an environment where integration tests can be run
* **verify**:  run any checks to verify the package is valid and meets quality criteria.
* **install**: install the package into the local repository, for use as a dependency in other projects locally.
* **deploy**: done in an integration or release environment, copies the final package to the remote repository for sharing with other developers and projects.

Other builds:
* **clean**: cleans up artifacts created by prior builds.
* **site**: generates site documentation for this project. (A major aim of the refactoring in Maven 3 was to decouple the Maven core from Doxia 
and to allow arbitrary reporting systems to be developed. For this reason, all reporting related code has been removed from the core of Maven 3)

An interesting thing to note is that phases and goals may be executed in sequence.
```
mvn clean dependency:copy-dependencies package
```
This command will clean the project, copy dependencies, and package the project (executing all phases up to **package**)


## Reference
* [Maven in 5 Minutes](https://maven.apache.org/guides/getting-started/maven-in-five-minutes.html) - Apache Maven Docs
