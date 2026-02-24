pipeline {
    agent any

    tools {
        maven 'Maven-3.9.12'   // Configure this in Global Tool Configuration
        jdk 'JDK-25.0.2'
    }

    stages {

        stage('Checkout') {pipeline {
    agent any

    tools {
    maven 'maven'
    jdk 'jdk-21'
}


    stages {
        stage('Checkout Code') {
            steps {
                git branch: 'main', url: 'https://github.com/vaiii05/exp4.git'
                 
            }
        }

        stage('Build with Maven') {
            steps {
                bat 'mvn clean package'
            }
        }

        stage('Deploy to Tomcat') {
            steps {
                deploy adapters: [
                    tomcat9(
                        credentialsId: 'tomcat-creds',
                        path: '',
                        url: 'http://localhost:8081'
                    )
                ],
                contextPath: 'my-web-app',
                war: 'target/*my-web-app.war'
            }
        }
    }
}
            steps {
                git 'https://github.com/vaiii05/exp4.git'
            }
        }

        stage('Build') {
            steps {
                bat 'mvn clean package'
            }
        }

        stage('Archive WAR') {
            steps {
                archiveArtifacts artifacts: 'target/*.war', fingerprint: true
            }
        }
    }
}
