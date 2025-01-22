pipeline {
    agent any

    tools {
        maven 'Maven'
    }

    stages {
        stage("Build") {
            steps {
                sh 'mvn clean package'
            }
        }

        stage("SonarQube") {
            steps {
                script {
                    withSonarQubeEnv('servercyber') {
                        sh 'mvn sonar:sonar'
                    }
                }
            }
        }
    }
}
