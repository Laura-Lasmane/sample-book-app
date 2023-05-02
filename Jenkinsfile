pipeline {
    agent any

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
                    deploy("DEV")
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
                    deploy("STG")
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
                    deploy("PRD")
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
def deploy(String environment){
    echo "Build to ${environment} has started.."
}

def test(String environment){
    echo "Testing on ${environment} has started.."
}

def build(){
    echo "Build of node application is starting.."
}