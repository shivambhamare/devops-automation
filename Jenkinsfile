pipeline {
    agent any
    environment{
        PATH = "/usr/share/maven/bin:$PATH"
    }
    stages{
        stage('Build Maven'){
            steps{
                checkout([$class: 'GitSCM', branches: [[name: '*/main']], extensions: [], userRemoteConfigs: [[url: 'https://github.com/shivambhamare/devops-automation']]])
                sh 'mvn clean install'
            }
        }
        stage('Build docker image'){
            step{
                sh 'docker build -t shivam/devops-integration .'
            }
        }
    }
}
