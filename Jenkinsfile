
pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                echo "Building..."
                sh 'exit 1' // fail intentionally
            }
        }
    }
    post {
        success {
            githubNotify context: 'CI', description: 'Build passed', status: 'SUCCESS'
        }
        failure {
            githubNotify context: 'CI', description: 'Build failed', status: 'FAILURE'
        }
    }
}
