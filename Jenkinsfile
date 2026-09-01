pipeline {
    agent any

    stages {

        stage('Checkout') {
            steps {
                echo 'Code has been checked out by Jenkins'
            }
        }

        stage('Build') {
            steps {
                echo 'Starting build...'
                sh 'chmod +x app.sh'
            }
        }

        stage('Test') {
            steps {
                echo 'Running application test...'
                sh './app.sh'
            }
        }

        stage('Docker Check') {
            steps {
                echo 'Checking Docker...'
                sh 'docker --version'
            }
        }

    }
     
stage('Docker Build') {
    steps {
        sh 'docker build -t jenkins-demo:1.0 .'
    }
}

    post {
        success {
            echo '🎉 Pipeline completed successfully!'
        }

        failure {
            echo '❌ Pipeline failed!'
        }
    }
}
