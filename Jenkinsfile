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
                echo "${env.BRANCH_NAME}"
                echo "${env.BUILD_NUMBER}"
                echo "${env.BUILD_ID}"
                echo "${env.BUILD_DISPLAY_NAME}"
                echo "${env.JOB_NAME}"
                echo "${env.JENKINS_HOME}"
                echo "${env.JENKINS_URL}"
                echo "${env.JOB_URL}"
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
