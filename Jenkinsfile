
node('docker_pt') {
  stage ('Promote build in Artifactory'){
    environment {
     RESPATH = "http://10.0.2.15:8081/artifactory/api/storage/example-project/${BUILD_NUMBER}/hello-0.0.1.war?properties=Performance-Tested=Yes"
    }
    sh "echo ***********${RESPATH}************"
    withCredentials([usernameColonPassword(credentialsId:
      'artifactory-account', variable: 'credentials')]) {
        sh 'curl -u${credentials} -X PUT http://10.0.2.15:8081/artifactory/api/storage/example-project/${BUILD_NUMBER}/hello-0.0.1.war?properties=Performance-Tested=Yes';
      }
  }
}
