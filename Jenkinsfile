pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                sh 'java -version'
                sh 'mvn -version'
                sh 'mvn clean verify'
            }
        }

        stage('SonarQube Analysis') {
            steps {
                withSonarQubeEnv('SonarQube') {
                    sh 'mvn sonar:sonar -Dsonar.projectKey=myapp'
                }
            }
        }
    }
}
