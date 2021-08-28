pipeline{
	agent any
	stages{
		stage("Pull Latest Image"){
			steps{
				sh "docker pull kaosjaviier/docker-advance-framework"
			}
		}
		stage("Start Grid"){
			steps{
				sh "docker-compose up -d hub chrome firefox"
			}
		}
		stage("Run Test"){
			steps{
				sh "docker-compose up smoke-module"
			}
		}
	}
	post{
		always{
			sh "docker-compose down"
		}
	}
}