pipeline {
    agent any

    stages {

        stage('Checkout') {
            steps {
                echo 'Repository checked out successfully.'
            }
        }

        stage('Build') {
            steps {
                dir('case-studies-jenkins/spring-boot-app') {
                    sh 'chmod +x mvnw'
                    sh './mvnw clean package'
                }
            }
        }
    }
}
