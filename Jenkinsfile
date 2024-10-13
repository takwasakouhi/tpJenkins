pipeline {
    agent any

    stages {
        stage('Git') {
            steps {
                git branch: 'main',
                url: 'https://github.com/takwasakouhi/tpJenkins.git'
            }
        }

        stage('Build') {
            steps {
                sh 'mvn clean install'
            }
        }

        stage('Sonarqube analysis') {
            steps {
                withSonarQubeEnv('sonarqube'){
                    sh 'mvn sonar:sonar'
                }
            }
        }
    }
}
