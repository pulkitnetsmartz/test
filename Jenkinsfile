pipeline {
     agent any
     stages {
        stage("Build") {
            steps {
                sh "npm install"
                sh "npm run build"
            }
        }
        stage("Deploy") {
            steps {
                sh "sudo rm -rf /var/lib/jenkins/workspace/jenkins connection"
                sh "sudo cp -r ${WORKSPACE}/build/ "/var/lib/jenkins/workspace/jenkins connection""
            }
        }
    }
}
