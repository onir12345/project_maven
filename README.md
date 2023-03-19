jenkins pipeline script for automaiton of mvn project.
pipeline {
    agent any 
    stages {
        stage('git repo & clean') {
            steps {
                sh "rm -rf project_maven"
                sh "git clone https://github.com/onir12345/project_maven.git" 
                sh "mvn clean -f project_maven"
            }
        }
        stage('test') {
            steps {
                sh "mvn test -f project_maven"
            }
        }
        stage('deploy') {
            steps {
                sh "mvn package -f project_maven"
            }
        }
    }
}
