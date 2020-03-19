#!/usr/bin/env groovy
node('master'){
    def VERSION = '2.0'
	
	stage ('checkout'){
		checkout scm
	}
	
	stage ('build') {
		sh '/opt/apache-maven-3.1.1/bin/mvn clean package'
	}
	
	stage ('static analysis') {
		sh '/opt/apache-maven-3.1.1/bin/mvn findbugs:findbugs'
	} 
	
	stage ('sonarqube analysis'){
		withSonarQubeEnv('sonarqube'){
			sh "/opt/apache-maven-3.1.1/bin/mvn sonar:sonar"
		}
	}
}