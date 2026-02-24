pipeline {
    agent any

    tools {
        maven 'Maven 3.9.12'   // Configure this in Global Tool Configuration
    }

    stages {

        stage('Checkout') {
            steps {
                git 'https://github.com/vaiii05/exp4.git'
            }
        }

        stage('Build') {
            steps {
                sh 'mvn clean package'
            }
        }

        stage('Archive WAR') {
            steps {
                archiveArtifacts artifacts: 'target/*.war', fingerprint: true
            }
        }
    }
}
