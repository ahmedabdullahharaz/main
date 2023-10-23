pipeline{
    agent any
    stages{
        stage('build'){
            steps{
                script{
                    sh 'mvn clean package'
                }
            }
        }
        stage('test'){
            steps{
                script{
                    echo "test in progress"
                }
            }
        }
    }
post {
  success {
            slackSend channel: '#jenkins-ci', message: "success ${env.JOB_NAME} ${env.BUILD_NUMBER} (<${env.BUILD_URL}|Open>)", teamDomain: 'harazlabs', tokenCredentialId: 'slack-notification'
    // One or more steps need to be included within each condition's block.
  }
}

}