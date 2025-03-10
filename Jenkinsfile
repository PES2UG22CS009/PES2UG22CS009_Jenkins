pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Building the application...'
                sh 'g++ -o hello_exec hello.cpp'
            }
        }

        stage('Test') {
            steps {
                echo 'Testing the application...'
                sh './hello_exec'
            }
        }

        stage('Deploy') {
            steps {
                echo 'Deploying the application...'
                sh 'mkdir -p /var/jenkins_home/deploy'
                sh 'mv hello_exec /var/jenkins_home/deploy/hello_exec'
            }
        }
    }

    post {
        success {
            echo 'Pipeline executed successfully!'
        }
        failure {
            echo 'Pipeline execution failed!'
        }
    }
}
