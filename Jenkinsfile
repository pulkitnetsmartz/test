pipeline {
    agent any
    tools {
        nodejs "NodeJS_Install" // Specify the Node.js installation ID
    }
    stages {
        stage("Build") {
            steps {
                sh "npm install"
            }
        }
        stage("Deploy") {
            steps {
                sh "npm run build"
            }
        }
    }
}
