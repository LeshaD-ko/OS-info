pipeline {

    agent {
        docker {
            image "maven:3.6.0-jdk-13"
            label "docker"
        }
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
                sh 'mvn clean package'
            } 
        }        
    }
    
    /*post {
        always {
          cleanWs()
        }
    }*/
}
