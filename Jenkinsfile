//Declerative pipeline
pipeline {
	//agent any
	agent { docker { image 'maven:3.6.3'} }
	stages {
		stage('Build') {
			steps {
				//sh 'mvn --version'
				echo "Build 9"
			}
		}
		stage('Test') {
			steps {
				echo "Test"
			}
		}
		stage('Integration Test') {
			steps {
				echo "Integration Test"
			}
		}
	} 
	post {
		always {
			echo "runs always"
		}
		success {
			echo "runs when successfull"
		}
		failure {
			echo "runs when fails"
		}
	}
}
