pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                script {
                    echo "Building the application..."
                    sh "make -C Downloads/CC_TA-main/main clean && make -C Downloads/CC_TA-main/main hello_exec"
                }
            }
        }

        stage('Test') {
            steps {
                script {
                    echo "Running tests..."
                    sh "./main/hello_exec"
                }
            }
        }

        stage('Deploy') {
            steps {
                script {
                    echo "Deploying application..."
                    sh 'echo "Deployment successful!"'
                }
            }
        }
    }

    post {
        failure {
            echo "Pipeline failed"
        }
        success {
            echo "Pipeline completed successfully!"
        }
    }
}
