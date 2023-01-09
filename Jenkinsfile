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
                echo "${currentBuild}.${currentResult}"
                echo "8888888888888888888888888888888888888888888"
            }
        }
    }
    post {
     always {
         echo "${currentBuild.currentResult}"
         emailext attachLog: true, body: "See ${BUILD_URL}", subject: "Jenkins: ${JOB_NAME}: Build status is ${currentBuild.currentResult}", to: 'yvagvsv@gmail.com'
     }
   }
}
