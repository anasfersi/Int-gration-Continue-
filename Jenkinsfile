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
                echo 'Deploying.....'
            }
        }
    }
    post {
        always {
              emailext body: '$DEFAULT_CONTENT',
                        recipientProviders: [[$class: 'DevelopersRecipientProvider'], [$class: 'RequesterRecipientProvider']],
                        subject: '$DEFAULT_SUBJECT'
            
        }
    }
    
}
