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
                sh 'docker build -t registry.cn-hangzhou.aliyuncs.com/huorepo/jenkins-demo:${BUILD_NUMBER} .'
            }
        }

        stage ('docker push') {
            steps {           
                sh 'docker login registry.cn-hangzhou.aliyuncs.com -u 274020988@qq.com -p 778825hh'
                sh 'docker push registry.cn-hangzhou.aliyuncs.com/huorepo/jenkins-demo:${BUILD_NUMBER}'
            }
        }

    }

}
