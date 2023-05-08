pipeline {
    agent any
    triggers{ pollSCM('*/1 * * * *') }
    stages {
// Būvējuma izveide        
        stage('Build') {
            steps {
                script{
                    build()
                }
            }
        }
// Būvējuma izvietošanu “DEV” vidē
        stage('Deploy to DEV') {
            steps {
                script{
                    deploy("DEV", 1010)
                }
            }
        }
// Testu izpildi “DEV” vidē
        stage('Test on DEV') {
            steps {
                script{
                    test("BOOKS", "DEV")
                }
            }
        }
// Būvējuma izvietošanu “STG” vidē
        stage('Deploy to STG') {
            steps {
                script{
                    deploy("STG", 1020)
                }
            }
        }
// Testu izpildi “STG” vidē
        stage('Test on STG') {
            steps {
                script{
                    test("BOOKS", "STG")
                }
            }
        }
// Būvējuma izvietošanu “PRD” vidē
        stage('Deploy to PRD') {
            steps {
                script{
                    deploy("PRD", 1030)
                }
            }
        }
// Testu izpildi “PRD” vidē
        stage('Test on PRD') {
            steps {
                script{
                    test("BOOKS", "PRD")
                }
            }
        }
    }
}

// Funkcijas definēšana
def build(){
    echo "Build of node application is starting.."
    bat "dir"
    bat "npm install"
    // bat "npm test"
}

def deploy(String environment, int port){
    echo "Deployment to ${environment} has started.."
    git branch: 'main', url: 'https://github.com/Laura-Lasmane/sample-book-app.git'
    bat "pm2 delete \"books-${environment}\""
    bat "pm2 start -n \"books-${environment}\" index.js -- ${port}"
}

def test(String test_set, String environment){
    echo "Testing ${test_set} test set on ${environment} has started.."
    git branch: 'main', poll: false, url: 'https://github.com/Laura-Lasmane/course-js-api-framework.git'
    bat "dir"
    bat "npm install"
    bat "npm run ${test_set} ${test_set}_${environment}"
}

