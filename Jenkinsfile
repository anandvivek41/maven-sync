pipeline {
    agent { label 'maven-label' }

    stages {
     stage('prepare') {
            steps {
                git branch: 'main', url: 'https://github.com/quick-abc/maven-sync.git'
            }
        }
        stage('build') {
            steps {
                sh 'mvn clean deploy'
                }
            }
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
