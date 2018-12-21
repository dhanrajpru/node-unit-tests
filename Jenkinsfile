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
                 withEnv(['PATH+EXTRA=/usr/sbin:/usr/bin:/sbin:/bin']
                 sh "npm install"
                //sh "npm run coverage"
                //sh "eslint -f json -o report.json ."
            }
        }
        stage("run sonarqube"){
            steps{
                sh "sonar-scanner"
            }
        }
    }
}     
