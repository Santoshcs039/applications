pipeline {
    agent any
    
    stages {
        
        stage('Checkout')
        {
            steps {
            checkout([$class: 'GitSCM',
                      branches: [[name: '*/main']],
                      userRemoteConfigs: [[url: 'https://github.com/Santoshcs039/applications.git',
                      ]]])
            }    

        }

        stage('Build') {
                       
            steps{
                    sh '''
                    sudo apt update && sudo apt install maven -y
                    ls -lrt
                    sleep 5
                '''
                }
         
        }
    
        stage('Test') {
        
            steps{
                
                sh '''
                cd java-maven-calculator-web-app
                
                mvn clean install
                '''

                
                }
            }


        }
    }
