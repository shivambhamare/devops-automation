pipeline {
    agent any
    environment{
        PATH = "/usr/share/maven/bin:$PATH"
    }
    tools{
        maven 'maven_3_5_0'
    }
    stages{
        stage('Build Maven'){
            steps{
                checkout([$class: 'GitSCM', branches: [[name: '*/main']], extensions: [], userRemoteConfigs: [[url: 'https://github.com/shivambhamare/devops-automation']]])
                sh 'mvn clean install'
            }
        }
    }
}
