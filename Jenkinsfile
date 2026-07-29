pipeline {
    agent {
        label 'docker'
    }

    stages {
        stage('System Info') {
            steps {
                sh 'hostname'
                sh 'whoami'
                sh 'pwd'
            }
        }
    }
}
