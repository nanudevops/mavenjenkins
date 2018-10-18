pipeline {
    agent { label 'linux' }
    tools {
        maven 'mvn'
    }
    stages {
        stage ('Checkout') {
          steps {
            git 'https://github.com/nanusahi/mavenjenkins.git'
          }
        }
        stage('Build') {
            steps {
                sh 'mvn clean compile'
            }
        }
        stage('Test'){
            steps {
                sh 'mvn test'
                junit '**/target/surefire-reports/TEST-*.xml'
            }
        }
        stage('Package') {
            steps {
                sh 'mvn package'
            }
        }
    }
}
