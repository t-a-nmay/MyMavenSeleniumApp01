pipeline {
	agent any
	
	tools {
		maven 'Maven'
		jdk 'JDK'
	}
	
	stages {
	
		stage('Checkout') {
			steps {
				git branch: 'master', url: 'https://github.com/t-a-nmay/MyMavenSeleniumApp01.git'
			}
		}
		
		stage('Build') {
			steps {
				sh 'mvn compile package'
			}
		}
		
		stage('Test') {
			steps {
				sh 'mvn test'
			}
		}	
		
		stage('Archive Artifacts') {
			steps {
				archiveArtifacts artifacts: 'target/*.jar', fingerprint: true
			}
		}	
	}
	
	post {
		success {
			echo 'Pipeline Successfull!'
		}
		failure {
			echo 'Pipeline Failed!'
		}
	}
}								
