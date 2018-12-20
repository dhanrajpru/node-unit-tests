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
                sh "eslint /usr/local/lib/node_modules/eslint/conf/eslint-recommended.js -f checkstyle ./node-unit-tests > eslint.xml"
            }
        }
    }
     
    post {
        always{
            dir ("/var/lib/jenkins/jobs/test/node-unit-test/") {
              step([$class: 'hudson.plugins.checkstyle.CheckStylePublisher', checkstyle: 'eslint.xml'])
            }
        }
    }
} 
