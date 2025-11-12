pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo "Build started..."
                sh 'ls -l'
            }
        }

        stage('Test') {
            steps {
                echo "Running simple tests..."
                sh 'if [ -f sample-text.html ]; then echo "sample-text.html exists, test passed!"; else echo "Test failed!"; exit 1; fi'
            }
        }

        stage('Deploy') {
            steps {
                echo "Deploying to web server..."
                sh 'sudo cp sample-text.html /usr/share/nginx/html/sample-text.html'
            }
        }
    }

    post {
        success {
            echo 'Pipeline completed successfully!'
        }
        failure {
            echo 'Pipeline failed!'
        }
    }
}