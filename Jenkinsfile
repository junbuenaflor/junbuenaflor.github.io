/* Requires the Docker Pipeline plugin */
pipeline {
    agent { docker { image 'php:8.2.9-alpine3.18' } }
    stages {
        stage('build') {
            steps {
                sh 'php --version'
            }
        }
        stage('Test') {
            steps {
                sh 'echo "Fail!"; exit 1'
            }
    }
    post {
        always {
            echo 'This will always run'
        }
        success {
            echo 'This will run only if successful'
        }
        failure {
            echo 'This will run only if failed'
        }
        unstable {
            echo 'This will run only if the run was marked as unstable'
        }
        changed {
            echo 'This will run only if the state of the Pipeline has changed'
            echo 'For example, if the Pipeline was previously failing but is now successful'
        }
    }
}
