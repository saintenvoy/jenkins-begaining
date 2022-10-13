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
                sh 'docker build -t registry.cn-hangzhou.aliyuncs.com/huorepo/jenkins-demo:${build_tag} .'
            }
        }

         stage('Push') {
            septs {
                sh "docker login -u 247020988@qq.com -p 778825hh"
                sh "docker push registry.cn-hangzhou.aliyuncs.com/huorepo/jenkins-demo:${build_tag}"
        }

    }
   
}
