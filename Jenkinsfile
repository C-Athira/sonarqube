node {
  stage('SCM') {
    checkout scm
  }
  stage('SonarQube Analysis') {
    def mvn = tool 'maven3';
    withSonarQubeEnv() {
      sh ''' mvn sonar:sonar -Dsonar.url=http://172.23.48.1/:9000/ -Dsonar.login=squ_68720c372cd212beb6225622a76afb3ad06c4b34 -Dsonar.projectName=jenkins-pipeline -Dsonar.java.binaries=. -Dsonar.projectKey=jenkins-pipeline -Dorg.jenkinsci.plugins.durabletask.BourneShellScript.HEARTBEAT_CHECK_INTERVAL=86400'''
    }
  }
}