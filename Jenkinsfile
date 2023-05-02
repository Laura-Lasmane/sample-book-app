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
                    test("DEV")
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
                    test("STG")
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
                    test("PRD")
                }
            }
        }
    }
}

// Funkcijas definēšana
def build(){
    echo "Build of node application is starting.."
    bat "dir"
    bat "npm install -g pm2"
}

def deploy(String environment, int port){
    echo "Deployment to ${environment} has started.."
    bat "pm2 start -n \"books-${environment}\" index.js -- ${port}"
}

def test(String environment){
    echo "Testing on ${environment} has started.."
}

