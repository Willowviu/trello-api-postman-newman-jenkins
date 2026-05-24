pipeline {
    agent any
    
    environment {
        POSTMAN_API_KEY = credentials("postman-api-key")
    }

    stages {
        stage('Running collection') {
            steps {
                sh 'newman --version'
                sh 'newman run https://api.postman.com/collections/29116084-5eee27da-daa3-41b0-b2b2-e9a17701235c?apikey=$POSTMAN_API_KEY --reporters cli,htmlextra --reporter-htmlextra-export newman/report.html'
            }
        }
    }
    
        post {
        always {
            publishHTML target: [
                reportName: 'Newman',
                reportDir: 'newman',
                reportFiles: 'report.html',
                reportTitles: 'Postman API tests',
                keepAll: true,
                alwaysLinkToLastBuild: true,
                allowMissing: false
            ]
        }
    }
}
