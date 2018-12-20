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
                sh "eslint -c /usr/local/lib/node_modules/eslint/conf/eslint-recommended.js -f checkstyle ./ > eslint.xml"
            }
        }
    }
     
        post{
            step([$class: 'hudson.plugins.checkstyle.CheckStylePublisher', checkstyle: '/var/lib/jenkins/jobs/test/node-unit-test/eslint.xml'])
            
        }
                 
    } 
    
      
       
  
