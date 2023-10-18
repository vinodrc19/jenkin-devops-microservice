//Declerative pipeline
pipeline {
	//agent any
	agent { 
		dockerContainer { 
			image 'maven:3.6.3'
		} 
	}
	stages {
		stage('Build') {
			steps {
				sh "mvn --version"
				echo "Build"
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
		//failure {
		//	echo "runs when fails"
		//}
	}
}
