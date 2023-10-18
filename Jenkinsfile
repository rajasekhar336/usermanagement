pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('SonarQube') {
  environment {
    SCANNER_HOME = tool 'sonar scanner jenkins'
    ORGANIZATION = "poc.net"
    PROJECT_NAME = "org.sonarqube:poc.net"
  }
  steps {
    withSonarQubeEnv('sonarqube') {
        bat "${SCANNER_HOME}/bin/sonar-scanner -Dsonar.organization=${ORGANIZATION} \
        -Dsonar.java.binaries=compiled \
        -Dsonar.projectKey=${PROJECT_NAME} \
        -Dsonar.sources=POCStudentCrud"
    }
  }
  }
}
}


            
