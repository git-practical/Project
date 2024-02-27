pipeline {
	agent any 
	
	stages {
	    stage('Checkout') {
	        steps {
			checkout scm			       
		      }}
		stage('Build') {
	           steps {
			  sh '/home/bharti/Documents/dev/apache-maven-3.9.6/bin/mvn install'
	                 }}
		stage('Deployment'){
		   steps {
		sh 'cp target/Project.war /home/bharti/Documents/dev/apache-tomcat-9.0.86/webapps'
			}}	
		stage('slack notification') {
			steps {
		slackSend baseUrl: 'https://hooks.slack.com/services/', channel: '#slack-one', color: 'good', message: 'this is first slack operation', teamDomain: 'New Workspace', tokenCredentialId: 'slack-test'
}}
