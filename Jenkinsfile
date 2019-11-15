pipeline {
    agent any
    tools { 
        maven 'Maven' 
    }
    stages {
        stage('Checkout') {
            steps {
                git 'https://github.com/nadejeT/mavenjenkins'
            }
        }
        stage('Build') {
            steps {
               bat label: '', script: 'mvn install'
   }
        }
        stage('Test') {
            steps {
                bat label: '', script: 'mvn test'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying....'
            }
        }
    }
}
