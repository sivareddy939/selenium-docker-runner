pipeline{
    agent any
    stages{
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
        stage("Bring grid down"){
            steps{
                bat "docker-compose down"
            }
        }
    }
}