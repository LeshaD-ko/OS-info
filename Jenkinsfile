pipeline {
    agent any
    tools {
        maven "MAVEN"
    }
    
    
    stages {
        stage('Build') {
            steps {
                git branch: '*/java-test', changelog: false, credentialsId: '7b76701c-4ba2-4942-973e-daad5cd0907d', poll: false, url: 'git@github.com:LeshaD-ko/OS-info.git'
                sh 'mvn --version'
                sh 'mvn clean install'
            }
        }
    }
    post {
        always {
          cleanWs()
        }
    }
}
