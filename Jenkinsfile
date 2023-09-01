node {
    stage('SCM Checkout'){
        git 'https://github.com/vsknalli/senthil-javaHome.git'
    }
    stage('Compile and package'){
        sh 'mvn package'
    }
    stage('Slack Notification'){
        slackSend baseUrl: 'https://hooks.slack.com/services/', 
        channel: '#devopscicd', 
        color: 'good', 
        message: 'Wellcome to all', 
        tokenCredentialId: 'slack2'
    }
}
