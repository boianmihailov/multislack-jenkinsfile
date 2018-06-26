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
            slackNotifier(currentBuild.currentResult)
            clientSlackNotifier(currentBuild.currentResult, "https://boianme.slack.com/services/hooks/jenkins-ci/", "slack-ci", "#ci", "boianme") 
            cleanWs()
        }
    }
}