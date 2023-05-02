pipeline {
    agent any

    stages {
// Būvējuma izveide        
        stage('Build') {
            steps {
                echo 'Build of node application is starting..'
            }
        }
// Būvējuma izvietošanu “DEV” vidē
        stage('Deploy to DEV') {
            steps {
                echo 'Deployment to DEV has started..'
            }
        }
// Testu izpildi “DEV” vidē
        stage('Test on DEV') {
            steps {
                echo 'Testing on DEV has started..'
            }
        }
// Būvējuma izvietošanu “STG” vidē
        stage('Deploy to STG') {
            steps {
                echo 'Deployment to STG has started..'
            }
        }
// Testu izpildi “STG” vidē
        stage('Test on STG') {
            steps {
                echo 'Testing on STG has started..'
            }
        }
// Būvējuma izvietošanu “PRD” vidē
        stage('Deploy to PRD') {
            steps {
                echo 'Deployment to PRD has started..'
            }
        }
// Testu izpildi “PRD” vidē
        stage('Test on PRD') {
            steps {
                echo 'Testing on PRD has started..'
            }
        }
    }
}