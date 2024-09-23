pipeline {
	agent any

	environment{
		dockerHome = tool 'myDocker'
		mavenHome = tool 'myMaven'
		PATH = "$dockerHome/bin:$mavenHome/bin:$PATH"
	}
	stages{
		stage('Checkout'){
			steps{
				sh 'mvn --version'
				sh 'docker version'
				echo "Build"

			}
		}
		stage('Compile'){
			steps{
				sh "mvn clean compile"
			}
		}
		stage('Test'){
			steps{
				sh "mvn test"
				

			}
		}
		stage('Package'){
			steps{
				
				sh "mvn package -Dskiptests"
			}
		}
		stage('Build Docker Image'){
			steps{
				// docker build -t omardevelopment/currency-exchange-devops:$env_BUILD_TAG

				script{
					dockerImage = docker.build("omardevelopment/currency-exchange-devops:${env_BUILD_TAG}")
				}
			}
		}
		
		stage('Push Docker Image'){
			steps{
				script{
					docker.withRegistry('','dockerhub'){
					dockerImage.push();
					dockerImage.push("latest");

				}

				}


			}
		}
	} 
	post{
		always{
			echo "I am Learning this stuff"
		}
		success{
			echo "I run when you are successful"
		}
		failure{
			echo " I Run When you fail. Failure"
		}
		changed{
			echo "something Changed IDK"
		}
	}
	
}
