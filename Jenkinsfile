pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                 sh 'ls -al'
            }
        }
        stage('Test') {
            steps {
                sh 'mvn clean test'
            }
        }
        stage('Package') {
            steps {
                sh '''
                mvn package
                '''
                archiveArtifacts artifacts: 'target/*.war', fingerprint: true
            }
        }
    }
}
