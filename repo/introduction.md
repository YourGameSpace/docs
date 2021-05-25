Title: Introduction

# Introduction

We run our own repository through which various things are made available.
For example, AntiCooldown or TubeTils can be implemented directly into your Maven-Project with just a few mouse clicks!

## Requirements

- Maven
- An IDE that supports Maven

## Usage

In order to access our Repository with Maven and then use it afterwards, the Repository itself must first be added. To do this, the following code snippet must be added to the pom.xml:

```xml
    <repositories>
        <repository>
            <id>repo.yourgamespace</id>
            <url>https://hub.yourgamespace.com/repo/</url>
        </repository>
    </repositories>
```
