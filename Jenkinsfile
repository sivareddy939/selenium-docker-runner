pipeline{
    agent any
    stages{
        stage("Pull Latest Image"){
            steps{
                bat "docker pull 608654/selenium-docker"
            }
        }
        stage("Start Grid"){
            steps{
                bat "docker-compose up -d selenium-hub chrome firefox"
            }
        }
        stage("Run Tests"){
            steps{
                bat "docker-compose up search-module book-flight-module"
            }
        }
    }
    post{
    	always{
    		archiveArtifacts artifacts: 'output/**'
    		bat "docker-compose down"
    	}
    }
}