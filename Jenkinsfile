pipeline {
    agent { node { label 'Agent_1' } }

    stages {
        stage('Build') {
            steps {
                echo 'Building..'
              sh '''
                ls -ltr
                pwd
                echo  "Hello from GitHub push webhook event"
              '''
            }
        }
        stage('Test') {
            steps {
                echo 'Testing..'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying....'
            }
        }
    }
    post { 
        always { 
            echo 'I will always run wether job is success or not'
        }
        success {
            echo 'I will run only when job is success'
        }
        failure {
            echo 'I will run only when job is fail'
        }
    }
}