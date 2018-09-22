pipeline {
    agent any
    tool name: 'localJDK', type: 'jdk'
    tools {
        maven 'localMaven'
    }

stages{
        stage('Build'){
            steps {
                bat 'mvn clean package'
            }
            post {
                success {
                    echo 'Now Archiving...'
                    archiveArtifacts artifacts: '**/target/*.war'
                }
            }
        }
    }
}
