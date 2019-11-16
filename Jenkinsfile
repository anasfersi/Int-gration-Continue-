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
                echo 'Deploying.... ... '
            }
        }
    }
    post {
        always {
            emailext body: "${currentBuild.currentResult}: Job ${env.JOB_NAME} build ${env.BUILD_NUMBER}\n More info at: ${env.BUILD_URL}",
                recipientProviders: [[$class: 'DevelopersRecipientProvider'],[$class: 'CulpritsRecipientProvider'], [$class: 'RequesterRecipientProvider']],
                subject: "Jenkins Build ${currentBuild.currentResult}: Job ${env.JOB_NAME}"
            
        }
    }
    
}
