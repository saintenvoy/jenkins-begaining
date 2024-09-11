def response = httpRequest customHeaders: [
     [name: 'App-Token', value: 'p4cUwbInKDHoTNnOUymAwkzpDsV7Gw5lNkpcUSFU'], 
     [name: 'Authorization', value: 'user_token Cm2zQITkuR7SmzqmpLwDO0EshkSB1bfDYD7abSu4'], 
     [name: 'Host', value: 'cncappdlv5055.asia.pwcinternal.com:8000']],
     url: "http://cncappdlv5055.asia.pwcinternal.com:8000/apirest.php/initSession"
def json = new JsonSlurper().parseText(response.content)
pipeline {
    agent any
    environment {
        branch = 'main'
        scmUrl = 'https://github.com/saintenvoy/jenkins-beginning.git'

    }
    stages {

          stage('Hello') {

     steps {
          echo "${json.message.keySet()}"
     }
  }
}
}
