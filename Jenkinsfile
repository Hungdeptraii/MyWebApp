pipeline {
    agent any
    stages {
        stage('Checkout') {
            steps {
                git 'https://github.com/Hungdeptraii/MyWebApp.git'  // Thay bằng repo của bạn
            }
        }
        stage('Build') {
            steps {
                sh 'mvn clean package'
            }
        }
        stage('Archive WAR') {
            steps {
                archiveArtifacts 'target/*.war'
            }
        }
    }
}
