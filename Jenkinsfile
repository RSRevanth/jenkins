pipeline {
    agent { node { label 'Agent_1' } }

    stages {
        stage('Build') {
            steps {
                echo 'Building..'
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
                error 'this is failure'
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