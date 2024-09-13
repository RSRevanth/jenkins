pipeline {
    agent { node { label 'Agent_1' } }
    options {
        // Timeout counter starts AFTER agent is allocated
        timeout(time: 1, unit: 'HOURS')
    }
    environment { 
        USER = 'Sattibabu'
    }

    stages {
        stage('Build') {
            steps {
                echo 'Building..'
               sh'''
                   ls -ltr
                   pwd
                   echo "Hello from GitHub push webhook event"
                   printenv
               '''
            }
        }
        stage('Test') {
            steps {
                echo 'Testing..'
            }
        }
        stage('Deploy') {
            steps{
                echo 'Deploying..'
            }
        }
        stage('Example') {
            environment { 
                AUTH = credentials('ssh-auth') 
            }
            steps {
                sh 'printenv'
            }
        }
    }

    post { 
        always { 
            echo 'I will always run whether job is success or not'
        }
        success{
            echo 'I will run only when job is success'
        }
        failure{
            echo 'I will run when failure'
        }
    }
}