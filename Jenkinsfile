pipeline {
    agent any
    stages {
        stage("checkout"){
            steps {
                checkout scm
            }
        }
<<<<<<< HEAD
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
=======
        /*stage("run eslint"){
            steps{
                sh "eslint -c /usr/lib/node_modules/eslint/conf/eslint-recommended.js -f checkstyle ./ > eslint.xml"
            }
        }*/
    }
     
    post {
        always{
            dir ("/var/lib/jenkins/workspace/test/") {
              step([$class: 'hudson.plugins.checkstyle.CheckStylePublisher', checkstyle: '/var/lib/jenkins/workspace/test/eslint.xml'])
            }
        }
    }
} 
>>>>>>> 3141dcc44afca2da056e27d98734674088e66a0f
