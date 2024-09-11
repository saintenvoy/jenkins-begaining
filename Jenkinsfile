def response =  httpRequest acceptType: "APPLICATION_JSON", 
     contentType: "APPLICATION_JSON", customHeaders: [
  {
    "App-Token": "p4cUwbInKDHoTNnOUymAwkzpDsV7Gw5lNkpcUSFU"
  },
  {
    "Authorization": "user_token Cm2zQITkuR7SmzqmpLwDO0EshkSB1bfDYD7abSu4"
  },
  {
    "Host": "cncappdlv5055.asia.pwcinternal.com:8000"
  }
],
     url: "http://cncappdlv5055.asia.pwcinternal.com:8000/apirest.php/initSession",
     validResponseCodes: '200:404'

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
          echo "response"
     }
  }
}
}
