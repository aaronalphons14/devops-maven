pipeline {
    agent any
    tools {
        maven 'Maven'
    }
    stages {
        stage('Checkout Git') {
            steps {
                git branch: 'main',
                    url: 'https://github.com/aaronalphons14/devops-maven.git'
            }
        }
        stage('Build and Test') {
            steps {
                bat 'mvn clean test'
            }
        }
    }
}
