pipeline {
    agent any
    stages {
        stage("checkout"){
            steps {
                checkout scm
            }
        }
        stage("unit testing"){
            steps{
                sh "npm run npm run coverage"
                sh "eslint -f json -o report.json ."
            }
        }
        stage("run sonarqube"){
            steps{
                sh "sonar-scanner"
            }
        }
    }
}     