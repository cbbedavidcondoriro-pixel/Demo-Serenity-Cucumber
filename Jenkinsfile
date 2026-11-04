pipeline {
    agent any
    stages {
        stage('Checkout') {
            steps {
                git branch: 'master', url: 'https://github.com/cbbedavidcondoriro-pixel/Demo-Serenity-Cucumber.git'
            }
        }
        stage('Build & Test') {
            steps {
                bat 'mvn clean verify'
            }
        }
        stage('Report') {
            steps {
                publishHTML([
                    allowMissing: true,
                    alwaysLinkToLastBuild: true,
                    keepAll: true,
                    reportDir: 'target/site/serenity',
                    reportFiles: 'index.html',
                    reportName: 'Serenity Report'
                ])
            }
        }
    }
}
