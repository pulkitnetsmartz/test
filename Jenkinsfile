pipeline {
    agent any
    
    stages {
        stage("Build") {
            steps {
                script {
                    // Build Docker image
                    sh "docker build -t myapp-image ."
                    
                    // Run Docker container from the built image
                    sh "docker run -d -p 80:80 myapp-image"
                }
            }
        }
        
        stage("Deploy") {
            steps {
                script {
                    // Remove existing contents of deployment directory
                    sh "sudo rm -rf /var/www/jenkins-react-app"
                    
                    // Copy build artifacts to deployment directory
                    sh "sudo cp -r ${WORKSPACE}/build/ /var/www/jenkins-react-app/"
                }
            }
        }
    }
}
