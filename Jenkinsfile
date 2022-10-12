pipeline {
    agent any
    environment {
        branch = 'main'
        scmUrl = 'git@github.com:saintenvoy/jenkins-beginning.git'

    }
    stages {
        stage('checkout git') {
            steps {
                git branch: branch, url: scmUrl
            }
        }

        stage('docker build') {
            steps {
                sh 'docker build -t nodoejs:latest .'
            }
        }

        stage ('test') {
            steps {           
                sh 'docker images'
            }
        }

    }
    post {
        failure {
            mail to: 'team@example.com', subject: 'Pipeline failed', body: "${env.BUILD_URL}"
        }
    }
}
