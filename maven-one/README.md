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

