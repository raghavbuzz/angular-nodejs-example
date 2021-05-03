pipeline {
    agent any
    stages {       
        stage('init') {
            steps {
                script {
                    echo "Initializing the application..."                                        
                }                
            }
        }  
        stage('build') {
            steps {
                script {               
                    echo "Building the application..."
                    sh 'npm --version'
                }                
            }
        }        
        stage('test') {
            steps {
                script {
                    echo "Testing the application..."
                }                
            }
        }    
        stage('deploy') {         
            steps {
                script {
                    def dockerCmd = 'docker run -d -p 3000:3080 raghavbuz/my-ng-app:1.0'
                    echo "Deploying the application..."
                    sshagent(['ec2-server-credentials']) {
                       sh "ssh -o StrictHostKeyChecking=no ec2-user@65.0.91.67 ${dockerCmd}"
                    }
                }
            }
        }
    }
}
