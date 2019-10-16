pipeline {
    agent any 
    stages {
        stage('Code Checkout') { 
            steps {
                git credentialsId: 'anshu8755993241', url: 'https://github.com/itraindevop/maven-example.git'
            }
        }
        stage('Build') { 
            steps {
              withMaven(jdk: 'JDK', maven: 'Maven') {
               sh 'mvn clean compile'
             }
            }
        }
        stage('Test') { 
            steps {
               withMaven(jdk: 'JDK', maven: 'Maven') {
               sh 'mvn test'
             }  
            }
        }
        stage('Package') { 
            steps {
              withMaven(jdk: 'JDK', maven: 'Maven') {
               sh 'mvn package'
             }  
            }
        }
        stage('Docker Image') { 
            steps {
             sh 'echo docker image is build'   
            }
        }
        stage('Deploy to Dev') { 
            steps {
             sh 'echo Deploy to Dev'   
            }
        }
        stage('Deploy to prod') { 
            steps {
              sh 'echo Deploy to Prod'  
            }
        }
    }
}
