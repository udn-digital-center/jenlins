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
                echo "Code Deploye
                sshagent (credentials: ['connetc_to_gcp_jenkins_demo_server']) {
                    sh 'ssh -o StrictHostKeyChecking=no jenkins@34.72.86.38'
                    sh 'ls -l'
                    //遠端機器的/var/www/html權限在ROOT下，所以要把jenkins的身分放進去root的GROUP
                    sh 'scp -r /var/jenkins_home/workspace/demo-html jenkins@34.72.86.38:/var/www/html' 
                    //sh 'cp -o StrictHostKeyChecking=no  -r /var/jenkins_home/workspace/pipline-demo /var/jenkins_home/workspace/test'
                }
            }
        }
    }
}
