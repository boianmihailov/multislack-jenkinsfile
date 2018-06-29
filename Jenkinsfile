/* import shared library */
@Library('jenkins-shared-library')_

pipeline {
    agent any

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
        /* Use slackNotifier.groovy from shared library and provide current build result as parameter */   
            /* slackNotifier(currentBuild.currentResult) */ 
            clientSlackNotifier(currentBuild.currentResult, "slack-token1", "https://boian.slack.com/services/hooks/jenkins-ci/",  "#build", "d9supnnbYF3sZuhbcBzrZZPd")

            clientSlackNotifier(currentBuild.currentResult, "slack-token2", "https://boianme.slack.com/services/hooks/jenkins-ci/",  "#jenkins", "vXXHOUUovoHajhIlcTg0IC4o") 
            cleanWs()
        }
    }
}