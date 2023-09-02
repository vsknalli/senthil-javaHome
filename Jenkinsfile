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

}
