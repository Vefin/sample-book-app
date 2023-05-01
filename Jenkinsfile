pipeline {
    agent any
    triggers{ pollSCM('*/1 * * * *') }


    stages {
        stage('Build') {
            steps {
                script{
                    build()
                }
            }
        }
        stage('Deploy to DEV') {
            steps {
                script{
                    deploy("DEV")
                }
            }
        }
        stage('Tests on DEV') {
            steps {
                script{
                    test("DEV")
                }
            }
        }
        stage('Deploy to STG') {
            steps {
                script{
                    deploy("STG")
                }
            }
        }
        stage('Tests on STG') {
            steps {
                script{
                    test("DEV")
                }
            }
        }
        stage('Deploy to PRD') {
            steps {
                script{
                    deploy("PRD")
                }
            }
        }
        stage('Tests on PRD') {
            steps {
                script{
                    test("DEV")
                }
            }
        }
    }
}

def deploy(String environment){
    echo "Deployment to ${environment} has started.."
}

def test(String environment){
    echo "Testing to ${environment} has started.."
}

def build(){
    echo "Building of node application is starting.."
}

  //Būvējuma izveidi;
  //Būvējuma izvietošanu “DEV” vidē;
  //Testu izpildi “DEV” vidē;
  //Būvējuma izvietošanu “STG” vidē;
  //Testu izpildi “STG” vidē;
  //Būvējuma izvietošanu “PRD” vidē;
  //Testu izpildi “PRD” vidē;