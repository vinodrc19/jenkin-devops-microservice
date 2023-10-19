//Declerative pipeline
pipeline {
	agent any
	//agent { 
		//label "docker" { 
		//dockerContainer {	
		//	docker pull maven:3.6.3
		//	//image 'maven:3.6.3'
		//	//image 'maven:3.6.0-jdk-8'
		//} 
	//}
	stages {
		stage('Pull Docker Image') {
            steps {
                script {
                    // Define the name of the Docker image and tag you want to pull
                    def imageName = 'maven'
                    def imageTag = '3.6.0-jdk-8'

                    // Pull the Docker image
                    //def dockerImage = docker.image("${imageName}:${imageTag}")
					def dockerImage = docker.image("maven:3.6.0-jdk-8")


                    // Pull the image
                    dockerImage.pull()

                    // You can also specify additional options if needed
                    // dockerImage.pull('--all-tags')
                }
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
