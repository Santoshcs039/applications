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
                    ls -lrt
                    sleep 5
                '''
                }
         
        }
    
        stage('Test') {
        
            steps{
                
                sh '''
                cd java-maven-calculator-web-app
                sudo mvn clean install -y
                '''

                
                }
            }


        }
    }
