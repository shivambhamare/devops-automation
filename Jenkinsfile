pipeline {
    agent any
    stages {
        stage('Build Maven') {
            steps {
                checkout([$class: 'GitSCM', branches: [[name: '*/main']], userRemoteConfigs: [[url: 'https://github.com/shivambhamare/devops-automation']]])
                sh 'mvn clean install'
            }
        }
        stage('Build Docker Image') {
            steps {
                sh 'docker build -t test-image .'
            }
        }
    }
}
