pipeline {
    agent {
        docker {
            image 'composer:latest'
        }
    }
    stages {
        stage('Build') {
            steps {
                sh 'composer install'
            }
        }
        stage('Test') {
            steps {
                sh './vendor/bin/phpunit tests'
            }
        }
        stage('Debug') {
            steps {
                echo "JD_TO_PULL: ${env.JD_TO_PULL}"
            }
        }
    }
}
