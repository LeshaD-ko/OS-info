pipeline {
    agent any
    tools {
        maven "MAVEN"
    }
    
    
    stages {
        stage ('Code analyse') {
            steps {
                sh 'echo "Run some lines"'
                }
        }
        stage ('Test') {
            steps {
                sh 'echo "some tests"'
            }
        }
        stage('Build') {
            steps {                
                sh 'mvn --version'
                sh 'mvn clean install package'
            } 
        }        
    }
    
    /*post {
        always {
          cleanWs()
        }
    }*/
}
