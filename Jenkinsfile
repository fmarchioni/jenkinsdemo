pipeline {
    agent any
    parameters {
        string(name: 'GIT_URL', defaultValue: 'https://github.com/fmarchioni/jenkinsdemo', description: 'Git repository URL')
    }
    stages {
        stage('Checkout') {
            steps {
                 echo "Cloning repository"
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
