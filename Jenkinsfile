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
                sh eslint -c /usr/local/lib/node_modules/eslint/conf/eslint-recommended.js -f checkstyle ./ > eslint.xml
            }
        }
    }
     
       post{
            always{
                dir ( "/var/lib/jenkins/jobs/test/node-unit-test/" ) {
                step([$class: 'CheckStylePublisher', pattern: '**/eslint.xml', unstableTotalAll: '0', usePreviousBuildAsReference: true])
            }
        }
     }
}
