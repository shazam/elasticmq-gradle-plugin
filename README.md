ElasticMQ Gradle Plugin
=======================

This is a Gradle plugin that enables the starting/stopping of an ElasticMQ instance for the purposes of testing

Usage
-----

<pre>
buildscript {
	repositories {
		mavenCentral()
	}

	dependencies {
		classpath "com.shazam.elasticmq-plugin:0.1"
	}
}

apply plugin: 'elasticmq'
</pre>

The ElasticMQ server will be automatically terminated upon exit of the Gradle script.

Tasks
-----

This plugin adds two tasks:
<pre>
startElasticMq
runElasticMq
</pre>

startElasticMq will bring up the server in the background.
runElasticMq will bring up the server and wait until the script is killed.  This is useful when you just want to run the server, perhaps while running tests in your IDE.

Configuration
-----
The port ElasticMQ will use can be configured through the elasticmq project extension, for example the following snippet will start on port 9320:
<pre>
apply plugin: 'elasticmq'

elasticmq {
	port = 9320
}
</pre>

If no port number is specified, the default of 9000 will be used

Project Status
-----
The current stable version is 0.1 and is available from Maven central as 'com.shazam:elasticmq-plugin:0.1'


