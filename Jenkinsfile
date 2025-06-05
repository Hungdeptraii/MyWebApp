pipeline {
    agent any

    tools {
        maven 'Maven3'     // cấu hình tên Maven trong Jenkins
        jdk 'Java17'       // tên JDK cấu hình trong Jenkins
    }

    stages {
        stage('Checkout') {
            steps {
                git 'https://github.com/Hungdeptraii/MyWebApp.git'
            }
        }

        stage('Build WAR') {
            steps {
                sh 'mvn clean package'
            }
        }

        stage('Deploy to Tomcat') {
            steps {
                script {
                    def warFile = "target/MyWebApp.war"
                    def tomcatWebapps = "C:\\apache-tomcat-10.1.41\\webapps\\"

                    bat "copy ${warFile} ${tomcatWebapps}"
                }
            }
        }
    }
}
