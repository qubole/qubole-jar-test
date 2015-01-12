# Introduction
This repository provides examples for compiling your code with qubole's hadoop jars. Qubole's maven repository is hosted in a paid S3 bucket `s3://paid-qubole/maven/`

This repository contains a list of example projects.

1. [hadoop20](haoop20/) - Use Qubole's hadoop-0.20 jars.

# Setup

You'll have to register Qubole's maven repository in your settings. Open up Maven settings file. Typically settings are stored in `~/.m2/settings.xml`. Add the following configuration parameters:


    <servers>
      ....
      <server>
        <!-- If you change the id, pom.xml in projects have to be edited too -->
        <id>qubole-s3-releases</id>
        <username>[AWS ACCESS KEY]</username>
        <password>[AWS SECRET KEY]</password>
      </server>
      <server>
        <!-- If you change the id, pom.xml in projects have to be edited too -->
        <id>qubole-s3-snapshots</id>
        <username>[AWS ACCESS KEY]</username>
        <password>[AWS SECRET KEY]</password>
      </server>
      ...
    </servers>
    
Alternatively, the access and secret keys for the account can be provided using

1. `AWS_ACCESS_KEY_ID` (or `AWS_ACCESS_KEY`) and `AWS_SECRET_KEY` (or `AWS_SECRET_ACCESS_KEY`) environment variables
2. `aws.accessKeyId` and `aws.secretKey` system properties
3. The Amazon EC2 [Instance Metadata Service](  http://docs.aws.amazon.com/AWSJavaSDK/latest/javadoc/com/amazonaws/auth/InstanceProfileCredentialsProvider.html)

Please refer to [AWS Maven](https://github.com/spring-projects/aws-maven) for more information. 
