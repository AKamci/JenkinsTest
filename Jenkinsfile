pipeline {
    agent any

    stages {
        stage('Build') {
            when {
                branch 'dev' // Sadece 'dev' branch'inde çalışacak
            }
            steps {
                echo 'Building on dev...'
                echo 'Waiting for 5 minutes...'
                sleep time: 5, unit: 'MINUTES' // 5 dakika bekleme
                // Örneğin: sh 'mvn clean install'
            }
        }
        stage('Test') {
            when {
                branch 'feature/*' // 'feature/*' isimli branch'lerde çalışacak
            }
            steps {
                echo 'Testing feature branch...'
                // Örneğin: sh 'mvn test'
            }
        }
        stage('Integration Test') {
            when {
                branch 'stable' // Sadece 'stable' branch'inde çalışacak
            }
            steps {
                echo 'Running integration tests on stable...'
                // Örneğin: sh 'mvn verify'
            }
        }
        stage('Staging Deployment') {
            when {
                branch 'stage' // Sadece 'stage' branch'inde çalışacak
            }
            steps {
                echo 'Deploying to staging...'
                // Örneğin: sh './deploy --env stage'
            }
        }
        stage('Production Deployment') {
            when {
                branch 'prod' // Sadece 'prod' branch'inde çalışacak
            }
            steps {
                echo 'Deploying to production...'
                // Örneğin: sh './deploy --env prod'
            }
        }
    }
}
