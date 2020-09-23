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
                sh 'echo "This is some text in a file for build" > test.txt'
                sh "echo ${BUILD_NUMBER} >> test.txt"
                sh 'ls -lart && pwd'
            }
        }
        stage('Archive'){
            steps {
                archiveArtifacts artifacts: 'test.txt'
            }
        }
    }
}
