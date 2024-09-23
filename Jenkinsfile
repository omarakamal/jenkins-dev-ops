pipeline {
	agent any

	environment{
		dockerHome = tool 'myDocker'
		mavenHome = tool 'myMaven'
		PATH = "$dockerHome/bin:$mavenHome/bin:$PATH"
	}
	stages{
		stage('Build'){
			steps{
				sh 'mvn --version'
				sh 'docker version'
				echo "Build"

			}
		}
		stage('Test'){
			steps{
				sh "mvn --version"
				echo "Test"

			}
		}
		stage('Integration Test'){
			steps{
				echo "Integration Test"

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
