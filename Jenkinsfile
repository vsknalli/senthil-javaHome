node {
    stage('SCM Checkout'){
        git 'https://github.com/vsknalli/senthil-javaHome.git'
    }
    stage('Compile and Package')
    sh 'mvn package'

    stage('SonarQube Analysis'){
        def mvnHome = tool name: 'maven', type: 'maven'
        withSonarQubeEnv('sonarqube'){
            sh "${mvnHome}/bin/mvn sonar:sonar"
        }
    }
    stage('Slack Notification'){
        slackSend baseUrl: 'https://hooks.slack.com/services/', 
        channel: '#devopscicd', 
        color: 'good', 
        message: 'Wellcome to all', 
        tokenCredentialId: 'slack2'
    }
}