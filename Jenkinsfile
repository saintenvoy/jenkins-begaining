import groovy.json.JsonSlurper

def response = httpRequest customHeaders: [
     [name: 'App-Token', value: 'n44pbVOuvNWTxt5GQd1uDFzJkRX9NbcqmW82jpS2'], 
     [name: 'Authorization', value: 'user_token 4T7vSS3xVJmkrYtBnJsbdehrnfQxKC3dzmkqnn7s'], 
     [name: 'Host', value: 'localhost']],
     url: "http://localhost/apirest.php/initSession"

def json = new JsonSlurper().parseText(response.content)

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

        stage('Hello') {
          steps {
            echo "${json.message.keySet()}"
     }
  }
}
}
