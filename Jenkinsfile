//Declerative pipeline
pipeline {
	agent any
	//agent {
	//	docker {
	//		image "maven:3.6.0-jdk-8"
	//	}
	//}
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
                    // Define the Docker image to use
                    def dockerImage = docker.image('maven:3.6.3')

                    // Run Docker commands within the container
                    dockerImage.inside {
                        sh 'mvn clean install'  // Replace with your build commands
                        sh 'docker build -t my-custom-image .'
                        sh 'docker push my-custom-image'
                    }
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
