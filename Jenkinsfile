node {
  stage('SCM') {
    git 'https://github.com/rajasekhar336/usermanagement.git'
  }
  stage('SonarQube analysis') {
    def scannerHome = tool 'SonarScanner 4.0';
    withSonarQubeEnv('sonarqube') { // If you have configured more than one global server connection, you can specify its name
      sh "${scannerHome}/bin/sonar-scanner"
    }
  }
}



            
