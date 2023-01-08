pipeline {
    agent any
    
    options{
        timestamps()
    }
    stages {
        stage('Build') {
            steps {
                echo 'Building..'
            }
        }
        stage('Test') {
            steps {
                echo 'Testing..'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying....'
            }
        }
    }
    post {
     always {
         emailext attachLog: true, body: "See ${BUILD_URL}", subject: "Jenkins: ${JOB_NAME}: Build status is ${currentBuild.currentResult}", to: 'yvagvsv@gmail.com'
     }
   }
}
