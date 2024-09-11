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

        cmd """curl --location --request GET "http://cncappdlv5055.asia.pwcinternal.com:8000/apirest.php/initSession" --header "App-Token: p4cUwbInKDHoTNnOUymAwkzpDsV7Gw5lNkpcUSFU" --header "Authorization: user_token Cm2zQITkuR7SmzqmpLwDO0EshkSB1bfDYD7abSu4" --header "Host: cncappdlv5055.asia.pwcinternal.com:8000"
"""

     }
  }
}
}
