pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        

        stage('Code Analysis') {
            steps {
                script {
                    def scannerHome = tool name: ' SonarQube', type: 'hudson.plugins.sonar.MsBuildSQRunnerInstallation'
                    withSonarQubeEnv('sonarqube') {
                        sh "${scannerHome}/bin/sonar-scanner"
                    }
                }
            }
        }
    }
}
