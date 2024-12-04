pipeline {
    agent any

    stages {
        stage('Build') {
            when {
                branch 'dev'
            }
            steps {
                echo 'Building on dev...'
                // Örneğin: sh 'mvn clean install'
            }
        }
        stage('Test') {
            when {
                branch 'feature/*'
            }
            steps {
                echo 'Testing feature branch...'
                // Örneğin: sh 'mvn test'
            }
        }
        stage('Integration Test') {
            when {
                branch 'stable'
            }
            steps {
                echo 'Running integration tests on stable...'
                // Örneğin: sh 'mvn verify'
            }
        }
        stage('Staging Deployment') {
            when {
                branch 'stage'
            }
            steps {
                echo 'Deploying to staging...'
                // Örneğin: sh './deploy --env stage'
            }
        }
        stage('Production Deployment') {
            when {
                branch 'prod'
            }
            steps {
                echo 'Deploying to production...'
                // Örneğin: sh './deploy --env prod'
            }
        }
    }
}