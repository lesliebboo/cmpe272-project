pipeline {
    agent any

    triggers {
        // Triggered by the GitHub webhook on every push to main
        githubPush()
    }

    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }
        stage('Build') {
            steps {
                bat '''
                    echo "=== Build stage ==="
                    echo "Listing workspace:"
                    dir /b
                    echo "Checking Python:"
                    python --version
                    echo "=== Build done ==="
                '''
            }
        }
        stage('Test') {
            steps {
                bat '''
                    echo "=== Test stage ==="
                    python -m pip install --quiet -r requirements.txt
                    python -m pytest tests/ -v
                    echo "=== Tests done ==="
                '''
            }
        }
    }

    post {
        always {
            echo "Pipeline finished (build #${env.BUILD_NUMBER})"
        }
        success {
            echo "BUILD SUCCESS"
        }
        failure {
            echo "BUILD FAILED"
        }
    }
}
