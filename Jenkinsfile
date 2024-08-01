pipeline{
    agent any
    stages{
        stage('checkout the code from github'){
            steps{
                 git url: 'https://github.com/TheWolfman74/star-agile-health-care.git'
                 echo 'github url checkout'
            }
        }
        stage('codecompile with venkat'){
            steps{
                echo 'starting compiling'
                sh 'mvn compile'
            }
        }
        stage('codetesting with venkat'){
            steps{
                sh 'mvn test'
            }
        }
        stage('qa with venkat'){
            steps{
                sh 'mvn checkstyle:checkstyle'
            }
        }
        stage('package with venkat'){
            steps{
                sh 'mvn package'
            }
        }
        stage('run dockerfile'){
          steps{
               sh 'docker build -t myimg .'
           }
         }
        stage('port expose'){
            steps{
                sh 'docker run -dt -p 8082:8082 --name c000 myimg'
            }
        }   
    }
}
