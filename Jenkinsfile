pipeline {
   
   tools{nodejs "npm"}

   agent any

    stages{
        stage('Initial'){
            steps{
                echo "-----Initial----------"
            }
        }
        stage('Build Image'){
            when{
                branch 'dev'
                environment{
                    registry = "thanakit2/nodeapp_UAT"
                }
                steps{
                    echo "-----Start Building Image UAT-----------"
                    script{
                         docker.build registry + ":$BUILD_NUMBER"
                    }
                }
            }
        }
        stage('Finish'){
            steps{
                echo "------Finish----------"
            }
        }
    }
   
}