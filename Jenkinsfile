pipeline {
    agent any  // Runs on any available agent

    stages {
        stage('Build') {
            steps {
                script {
                    echo 'Building C++ Project...'
                    sh 'g++ -o output main.cpp' // Compiling C++ file
                }
            }
        }

        stage('Test') {
            steps {
                script {
                    echo 'Running Tests...'
                    sh './output'  // Execute compiled binary
                }
            }
        }

        stage('Deploy') {
            steps {
                script {
                    echo 'Deploying...'
                    echo 'Deployment Successful ✅'
                }
            }
        }
    }

    post {
        failure {
            echo '🚨 Pipeline Failed! Check logs for errors.'
        }
    }
}
