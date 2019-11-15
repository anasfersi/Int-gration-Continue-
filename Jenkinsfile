pipeline {
    agent any
    stages {
        stage('CHECKOUT') {
            steps {
                git 'https://github.com/anasfersi/Integration-continue'
            }
        }
        stage('BUILD') {
            steps {
               bat label: '', script: 'mvn install'
   }
        }
        stage('TEST') {
            steps {
                bat label: '', script: 'mvn test'
            }
        }
        stage('DEPLOY') {
            steps {
                echo 'Deploying....'
            }
        }
    }
}
