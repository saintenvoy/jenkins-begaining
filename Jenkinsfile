def response =  httpRequest customHeaders: [
     [name: 'App-Token', value: 'p4cUwbInKDHoTNnOUymAwkzpDsV7Gw5lNkpcUSFU'], 
     [name: 'Authorization', value: 'user_token Cm2zQITkuR7SmzqmpLwDO0EshkSB1bfDYD7abSu4'], 
     [name: 'Host', value: 'cncappdlv5055.asia.pwcinternal.com:8000']],
     url: "http://cncappdlv5055.asia.pwcinternal.com:8000/apirest.php/initSession"

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
          echo "response()"
     }
  }
}
}
