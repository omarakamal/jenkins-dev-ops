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
		stage('Integration Test'){
			steps{
				sh "mvn failsafe:integration-test failsafe:verify"

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
