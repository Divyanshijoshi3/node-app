pipeline {
    agent any

    environment {
        NODEJS_HOME = tool 'NodeJS 18' // This must match the Node.js version in Jenkins
        PATH = "${NODEJS_HOME}/bin:${env.PATH}"
    }

    stages {
        stage('Clone Repository') {
            steps {
                git 'https://github.com/Divyanshijoshi3/node-app.git'
            }
        }

        stage('Install Dependencies') {
            steps {
                sh 'npm install'
            }
        }

        stage('Run Tests') {
            steps {
                sh 'npm test'  // Replace with actual test command if available
            }
        }

        stage('Build') {
            steps {
                sh 'npm run build'  // If your app has a build step
            }
        }

        stage('Deploy') {
            steps {
                sh 'scp -r . user@your-server:/var/www/node-app'  // Modify for your deployment method
            }
        }
    }
}
