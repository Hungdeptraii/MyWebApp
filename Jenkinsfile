pipeline {
    agent any

    tools {
        maven 'Maven3'     // Đúng với tên Maven bạn đã cấu hình trong Jenkins (Manage Jenkins > Global Tool Configuration)
        jdk 'Java21'       // Nếu bạn dùng Java 21 thì sửa lại thành 'Java21'
    }

    environment {
        WAR_FILE = "target\\MyWebApp.war"
        TOMCAT_WEBAPPS = "D:\\apache-tomcat-10.1.41\\webapps\\"
    }

    stages {
        stage('Checkout') {
            steps {
                git 'https://github.com/Hungdeptraii/MyWebApp.git'
            }
        }

        stage('Build WAR') {
            steps {
                bat 'mvn clean package'
            }
        }

        stage('Deploy to Tomcat') {
            steps {
                bat "copy /Y \"${env.WAR_FILE}\" \"${env.TOMCAT_WEBAPPS}\""
            }
        }
    }
}
