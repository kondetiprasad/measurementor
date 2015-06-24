# measurementor
measurementor helps you visualize data from your development cycle to help you be a better team.  This code is
used as an example data collection system in the book [Agile Metrics In Action](http://manning.com/davis2/).

# Development Branch
This is a new development branch for measurementor.  There are a bunch of changes in this branch:
- We're using [Spring Boot](http://projects.spring.io/spring-boot/) and [Node.js](https://nodejs.org/) instead of Grails
- A shiny interface that makes it easier to create and manage jobs
- Use Gradle to manage the build process
- Use Docker to manage containers for easier local development and deployments

# Getting Started

## Basic Stuff
Please install the following:
- [JDK](http://www.oracle.com/technetwork/java/javase/downloads/jdk8-downloads-2133151.html): Note that Java 7 also works for this project.
- [Gradle](https://gradle.org/): Used for the build of the application.

## [Elastic](https://www.elastic.co/)
You will have 2 options for elasticsearch environments in development.
- Install elastic on

## Additional Stuff
First note the [vagrant file](https://www.vagrantup.com/).  That will call the [puppet](http://puppetlabs.com/) manifest
that will install everything you need to get going.  In a nutshell it installs:
- [Elasticsearch](http://www.elasticsearch.org/) : used for indexing data for searching
- [Kibana](http://www.elasticsearch.org/guide/en/kibana/current/) : used for displaying pretty dashboards
- [MongoDB](http://www.mongodb.org/) : used to back the [Grails](https://grails.org/) based application
- [GVM](http://gvmtool.net/) : used to install Groovy and Grails
- [Groovy](http://groovy.codehaus.org/) : because Groovy is fun
- [Grals](https://grails.org/) : to run the data collector

Once you run:

    vagrant up

everything will get installed and you should have a box up and running.  Check elasticsearch and kibana
by navigating to the following URLs in your web browser of choice:

- local elasticsearch: [http://localhost:9200](http://localhost:9200)
- local kibana: [http://localhost:5601](http://localhost:5601)

To get the measurementor grails app running inside the vagrant box update the shared directory in your Vagrantfile on line 49.
This will share the source code on your local box with the appropriate directory on the Vagrant box.  Specifically, replace
[DIRECTORY WHERE YOU DOWNLOADED THE CODE] with the path on your dev machine where you downloaded this code.

Measurementor has a number of configurable settings including the URLs and credentials of the source systems and system defaults.
To update these variables you can just run the setup.sh script and it will prompt you to enter all the configurable values.


Get your vagrant box up and running:

    vagrant up

ssh into the vagrant box you just set up:

    vagrant ssh

Navigate to the directory that's shared with your dev machine for the measurementor grails app:

    cd /measurementor

Run the app:

    See [NOTES.md](NOTES.md)


thanks!

