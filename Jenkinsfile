pipeline {
    agent any
    stages{
        stage('Init'){
            steps {
                echo "Testing......"
            }
        }
    stage('Test'){
        steps {
            echo "Testing2......"
        }
        }    
 	stage('Build'){
            steps {
                echo "Building......"
            }
        }
 	stage('Deploy'){
            steps {
                echo "Code Deployed."
                sshagent (credentials: ['connetc_to_gcp_jenkins_demo_server']) {
                    sh 'ssh jenkins@34.72.86.38'
                    sh 'ls'
                   sh 'scp -r /var/jenkins_home/workspace/pipline-demo jenkins@34.72.86.38:/var/www/html' 
                }
            }
        }
    }
}
