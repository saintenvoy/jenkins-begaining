pipeline {
    agent any
    environment {
        branch = 'main'
        scmUrl = 'git@github.com:saintenvoy/jenkins-beginning.git'
        dockerhub = 'registry.cn-hangzhou.aliyuncs.com'
        DOCKERHUB_CREDENTIALS=credentials('dockerHub')

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
                sh 'docker build -t ${dockerhub}/huorepo/jenkins-demo:${BUILD_NUMBER} .'
            }
        }

        stage ('docker push') {
            steps {          
                echo "3. docker login & push"
                sh 'echo ${DOCKERHUB_CREDENTIALS_PSW} | docker login ${dockerhub} -u ${DOCKERHUB_CREDENTIALS_USR} --password-stdin'
                sh 'docker push ${dockerhub}/huorepo/jenkins-demo:${BUILD_NUMBER}'
            }
        }

         stage ('docker logout') {
            steps {          
                echo "3. docker logout"
                sh 'docker logout ${dockerhub}'
            }
        }

        stage ('YAML') {
            steps {
                echo "4. Change YAML File Stage"
                sh "sed -i 's/<BUILD_NUMBER>/${build_number}/' deploy.yaml"
                sh "sed -i 's/<BRANCH_NAME>/${env.BRANCH_NAME}/' deploy.yaml"
            }
            
        }

        stage('Deploy to rancher') {
            steps {
            echo "5. Deploy to rancher"
            sh "kubectl apply -f deploy.yaml"
            
            }
            
        }

    }

}
