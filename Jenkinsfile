pipeline {
    agent any

    environment {
      TEST_VAR = "TEST_VAR VALUE"
    }
    tools {
        maven 'mvn3.6.3' 
    }
    
    options {
        disableConcurrentBuilds()
    }
    
    stages {
      stage("TEST") {
          steps {
            echo env.TEST_VAR
            sh "mvn test"
          }
      }
      stage("Package") {
            steps {
                sh 'mvn package'
            }
      }
      stage('deploy') {
          steps {
              sh 'mvn install'
          }
      }
    }//stagges
    post {
        always {
          echo "This is a post action"
            //cleanWs()
        }
    }
}

