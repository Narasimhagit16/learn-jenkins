pipeline {
    agent {
        node {
            label 'AGENT-1'
        }
    }
    options {
        //timeout(time: 1, unit : 'SECONDS')
        disableConcurrentBuilds()
        
    }
    parameters {
        string(name: 'PERSON', defaultValue: 'Mr Jenkins', description: 'Who should I say hello to?')

        text(name: 'BIOGRAPHY', defaultValue: '', description: 'Enter some information about the person')

        booleanParam(name: 'TOGGLE', defaultValue: true, description: 'Toggle this value')

        choice(name: 'CHOICE', choices: ['One', 'Two', 'Three'], description: 'Pick something')

        password(name: 'PASSWORD', defaultValue: 'SECRET', description: 'Enter a password')
    }

    environment{
        GREETING= "Hello Jenkins"
    }
    stages {
        stage('Build') {
            steps {
                echo 'Building'
                echo "hello ${params.PERSON}"
            }
        }
        stage('Test'){
            steps {
                echo 'Testing'
            }
        }
        stage('Deploy') {
            steps {
                sh """
                  echo " hi     again"
                  echo "$GREETING"
                """
            }
        }

        stage('check parms')
        {
            steps {
                sh """  
                  echo "Hello ${params.PERSON}"
                  echo "Biography: ${params.BIOGRAPHY}"
                  echo "Toggle: ${params.TOGGLE}"
                    echo "Password: ${params.PASSWORD}"
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
