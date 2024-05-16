# Labo01 - Environment Setup

* [Labo description](https://cpnv-es-ngy.gitbook.io/vir1/labs/labo01-environment-setup)

## DevOps Stack to setup

Mention in this documentation the orders carried out and the results obtained.

If you have opted for a graphical installation, provide screenshots and describe the procedure up to the result obtained.

### Cloud cmd line interface - AWS Cli


- https://awscli.amazonaws.com/AWSCLIV2.msi

![img.png](img.png)


### IDE - Intellij


- https://www.jetbrains.com/idea/download/download-thanks.html?platform=windows


![img_1.png](img_1.png)

### Containers Engins - Docker

- https://desktop.docker.com/win/main/amd64/Docker%20Desktop%20Installer.exe?utm_source=docker&utm_medium=webreferral&utm_campaign=dd-smartbutton&utm_location=module&_gl=1*bwh3cn*_ga*NjgwMzUxNjc1LjE3MTM2Mzg3MzA.*_ga_XJWPQMJYHQ*MTcxNDAyNzc2Ni4zLjEuMTcxNDAyNzgxNS4xMS4wLjA.

![img_2.png](img_2.png)
![img_7.png](img_7.png)

### Versioning - Git + Git flow

- https://git-scm.com/download/win

![img_3.png](img_3.png)
![img_6.png](img_6.png)

### IDE Plugin - Docker plugin for IntelliJ

- Download the plugin from the IntelliJ marketplace

![img_4.png](img_4.png)

### Development Kit - JDK

- https://download.oracle.com/java/22/latest/jdk-22_windows-x64_bin.msi

![img_5.png](img_5.png)

### Package manager - Maven

- https://dlcdn.apache.org/maven/maven-3/3.9.6/binaries/apache-maven-3.9.6-bin.zip
- https://maven.apache.org/install.html

![img_8.png](img_8.png)

## Schema

Show your development environment, mentioning all the components in the stack.

Identify the links between components.

```
//TODO Schema
```

## Analysis

Answer the questions below, giving reasons for your answer (link, source).

### AWS CLI

* How does the AWS Cli interact with the cloud ?

```
When you use the AWS CLI, the AWS CLI sends the commands to the AWS cloud, and the cloud executes them.
```

* What other ways do we have of dialoging/interacting with the AWS cloud if we wanted to do without the CLI?

```
With the AWS management console, you can interact with the AWS cloud.
```

* What commands do I need to run in the CLI to start an ec2 instance?

```
aws ec2 run-instances --image-id ami-0c55b159cbfafe1f0 --count 1 --instance-type t2.micro --key-name MyKeyPair
```

### Docker Engine

* What type of hypervisor does Docker use?

```
Docker uses a type 2 hypervisor.
```

* What role does the Docker Desktop play in the Docker architecture?

```
Docker Desktop communicates with the Docker Engine to build, share and run containers.
```

### Java Environment

* JDK, JRE, JVM... what's the difference?

```
Java Dev Kit is only for developpers, Java Runetime Environment is a extendes version of the JVM with libraries (used on servers), Java Virtual Machine is the execution environment for Java applications.
```

### Maven

* What is the command you need to use Maven to retrieve dependencies (and only that)?

```

```


