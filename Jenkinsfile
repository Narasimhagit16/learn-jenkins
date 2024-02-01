pipeline {
    agent {
        node {
            label 'AGENT-1'
        }
    }
    environment{
        GREETING= "Hello Jenkins"
    }
    stages {
        stage('Build') {
            steps {
                echo 'Building'
            }
        }
        stage('Test'){
            steps {
                echo 'Testing'
            }
        }
        stage('Deploy') {
            steps {
                """
                  echo ' hi again'
                  echo $GREETING
                """
            }
        }
    } 
    post { 
        always { 
            echo 'I will always say Hello again!'
        }
        failure { 
            echo 'Pipeline failed!'
        }
        success { 
            echo 'I will always say when success'
        } 
    }
 }
