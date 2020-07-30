pipeline {
    agent any

    tools{nodejs "npm"}

    stages {

         stage('InitializeDocker'){
             steps{
                script{
                  def dockerHome = tool 'mydocker'
                }
             }
         }

         stage('Initial') {
            steps {
                echo "------Building-------"
                sh 'npm --version'
                sh 'npm install'
            }
        }
        stage('Build Image') {
             agent {
                 docker {
                    image 'node:10.0.0-alpine' 
                    args '-p 3000:3000' 
                }
            }
            steps{
                echo "-------Build-------"
            }

            steps {
                 script {
                     
                    def app = docker.build('thanakit2/jenkindemo')
                }
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying....'
            }
        }
    }
}