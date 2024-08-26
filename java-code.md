pipeline {
    agent any

    tools {
        maven 'Maven' // Use the Maven installation configured in Jenkins
    }

    stages {
        stage('Checkout') {
            steps {
                git 'https://github.com/madangitstudy/Jenkins-Zero-To-Hero.git'
            }
        }

        stage('Build') {
            steps {
                sh 'mvn clean package'
            }
        }

        stage('Test') {
            steps {
                sh 'mvn test'
            }
        }

        stage('Deploy') {
            steps {
                echo 'Deploy stage (for now, just echo)'
            }
        }
    }
}
