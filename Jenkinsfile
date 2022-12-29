 def sayHello(String a){
        echo "Hello $a"
    }

pipeline {
   
//    agent { label 'maven' }
    agent any

    stages {
     
        stage('greet') {
            steps{
                sayHello "Vivek"
            }
        }
     stage('prepare') {
            steps {
                git branch: 'main', url: 'https://github.com/anandvivek41/maven-sync.git'
            }
        }
//        stage('build') {
//            steps {
//                sh 'mvn clean deploy'
//                }
//            }
        stage('deploy-dev') {
            steps {
                echo "deploying an appln in devo"
            }
        }
         stage('deploy-stage') {
            steps {
                input 'Please provide approval for stage deployment'
                echo "deploying an appln in stage"
            }
        }
        stage('deploy-prod') {
            steps {
                input 'Please provide approval for prod deployment'
                echo "deploying an appln in prod"
            }
        }
    }
}
