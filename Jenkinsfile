pipeline {
    agent any
    environment {
        NODEJS_HOME = tool name: 'NodeJS', type: 'jenkins.plugins.nodejs.tools.NodeJSInstallation'
    }
    stages {
        stage("Build") {
            steps {
                sh "${NODEJS_HOME}/bin/npm install"
                sh "${NODEJS_HOME}/bin/npm run build"
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
