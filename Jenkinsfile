#!/usr/bin/env groovy
node('master'){
    def VERSION = '2.0'
	
	stage ('checkout'){
		checkout scm
	}
	
	stage ('build') {
		sh 'mvn clean source:jar package'
	}
	
	stage ('static analysis') {
		sh 'mvn findbugs:findbugs'
	} 
}