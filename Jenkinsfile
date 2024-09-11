pipeline {
    agent any
    environment {
        branch = 'main'
        scmUrl = 'https://github.com/saintenvoy/jenkins-beginning.git'

    }
    stages {
        stage('checkout git') {
            steps {
                echo "1. checkout git"
                git branch: branch, url: scmUrl
            }
        }

        stage('docker build') {
            steps {
                echo "2. docker build"
                sh 'docker build -t ${dockerhub}/${dockerhubrepo}/jenkins-demo:${BUILD_NUMBER} .'
            }
        }

        stage ('YAML') {
            steps {
                echo "4. Change YAML File Stage"
                sh "sed -i 's/<BUILD_NUMBER>/${BUILD_NUMBER}/' deploy.yaml"
                sh "sed -i 's/<BRANCH_NAME>/${env.BRANCH_NAME}/' deploy.yaml"
                sh "sed -i 's/<DOCKERHUB_NAME>/${dockerhub}/' deploy.yaml"
                sh "sed -i 's/<DOCKERHUB_REPO>/${dockerhubrepo}/' deploy.yaml"
            }
            
        }

        stage('Deploy to rancher') {
            steps {
            echo "5. Deploy to rancher"
            sh "kubectl apply -f deploy.yaml"
            
            }
            
        }

    }
    post {
        
        always {
            sh 'docker logout'
        }
    }

}
