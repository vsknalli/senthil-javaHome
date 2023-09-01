node {
    stage('SCM Checkout'){
        git 'https://github.com/vsknalli/senthil-javaHome.git'
    }
    stage('Compile and package'){
        sh 'mvn package'
    }
}
