pipeline {
     agent any
     stages {
        stage("Build") {
            steps {
                sh "docker build"
                sh "docker build -t host"
                sh "docker run -d -p 80:80 host"
            }
        }
        stage("Deploy") {
            steps {
                sh "sudo rm -rf /var/www/jenkins-react-app"
                sh "sudo cp -r ${WORKSPACE}/build/ /var/www/jenkins-react-app/"
            }
        }
    }
}
