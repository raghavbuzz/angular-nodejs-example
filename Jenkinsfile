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
                    echo "npm --version"
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
                }
            }
        }
    }
}
