pipeline {
    agent any 
    stages {
        stage('compile and clean') {
            steps { 
                sh "mvn clean compile"
            }
        }
        stage('test') {
            steps {
                sh "mvn test"
            }
        }
        stage('deploy') {
            steps {
                sh "mvn package"
            }
        }
      stage('archive') {
        steps { 
              archiveArtifacts '**/target/*.jar'
        }
        }
    }
}

