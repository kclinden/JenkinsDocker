pipeline {
    agent { label 'docker' }

    stages {
        stage('SCM') {
            steps {
                git 'https://github.com/kclinden/jenkinsdocker'
            }
        }
        stage('Hello'){
            steps {
                sh 'echo "Hello from Docker"'
                sh 'hostname'
            }
        }
    }
}
