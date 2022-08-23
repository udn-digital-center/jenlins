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
                sh "ls -l"
                sh "chmod +x  index.html" //changing permissions
                sh "chmod +x  style.css" //changing permissions
                sh "chmod +x  Jenkinsfile" //changing permissions
                sh "ls -l"
            }
        }
 	stage('Deploy'){
            steps {
                echo "Code Deployed."
                sshagent (credentials: ['connetc_to_gcp_jenkins_demo_server']) {
                    sh 'ssh jenkins@34.72.86.38'
                    sh 'ls -l'
                   sh 'scp -r /var/jenkins_home/workspace/pipline-demo jenkins@34.72.86.38:/var/www/html' 
                }
            }
        }
    }
}
