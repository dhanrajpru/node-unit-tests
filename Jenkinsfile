pipeline {
    agent any
    stages {
        stage("checkout"){
            steps {
                checkout scm
            }
        }
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
