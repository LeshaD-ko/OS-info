pipeline {
    agent any
    tools {
        maven "MAVEN"
    }
    
    
    stages {
        stage ('Code analyse') {
            sh 'echo "Run some lines"'
        }
        stage ('Test') {
            sh 'echo "some tests"'
        }
        stage('Build') {
            steps {                
                sh 'mvn --version'
                sh 'mvn clean install package'
            }
        }
        stage ('Deploy') {
            steps { 
                sh 'ssh ubuntu@3.65.39.24 rm -rf /var/www/temp_deploy/dist/'
                sh 'ssh ubuntu@3.65.39.24 mkdir -p /var/www/temp_deploy'
                sh 'scp -r dist ubuntu@3.65.39.24:/var/www/temp_deploy/dist/'
                sh 'ssh ubuntu@3.65.39.24 "rm -rf /var/www/example.com/dist/ && mv /var/www/temp_deploy/dist/ /var/www/example.com/"'
            }
        }
    }
    
    post {
        always {
          cleanWs()
        }
    }
}
