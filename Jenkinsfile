pipeline {
    agent any
    environment {
        IMAGE_NAME = 'raghavbuz/my-ng-app:2.0'
    }
    stages {       
        stage('init') {
            steps {
                script {
                    echo "Initializing the application..."  
                    // sh 'npm --version'                                      
                }                
            }
        }  
        stage('build') {
            steps {
                script {               
                    echo "Building the application..."                    
                    
                    // withCredentials([usernamePassword(credentialsId: 'docker-hub-credentials', passwordVariable: 'PASS', usernameVariable: 'USER')]){
                    //     sh "docker build -t ${IMAGE_NAME} ."
                    //     sh "echo  $PASS | docker login -u $USER --password-stdin"                        
                    //     sh "docker push ${IMAGE_NAME}"
                    // }                
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
                    echo "Deploying the application..."
                    def dockerCmd = "docker run -d -p 3000:3080 ${IMAGE_NAME}"                    
                    sshagent(['ec2-server-credentials']) {
                       // sh "ssh -o StrictHostKeyChecking=no ec2-user@13.232.70.217 ${dockerCmd}"
                      sh "docker --version"
                    }
                }
            }
        }
    }    
}
