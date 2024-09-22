pipeline {
	agent any

	stages{
		stage('Build'){
			steps{
				echo "Build"

			}
		}
		stage('Test'){
			steps{
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
