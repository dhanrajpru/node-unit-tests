pipeline {
    agent any
    stages {
        stage("checkout"){
            steps {
                checkout scm
            }
        }
        stage("run eslint"){
            steps{
                sh "eslint -c /usr/lib/node_modules/eslint/conf/eslint-recommended.js -f checkstyle /var/lib/jenkins/workspace/test/ > eslint.xml"
            }
        }
    }
     
    post {
        always{
            dir ("/var/lib/jenkins/workspace/test/") {
              step([$class: 'hudson.plugins.checkstyle.CheckStylePublisher', checkstyle: 'eslint.xml'])
            }
        }
    }
} 
