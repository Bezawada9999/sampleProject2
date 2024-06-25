
pipeline{
    agent any
    stages{
        stage('SCM'){
            steps{
            checkout scmGit(branches: [[name: '*/main']], extensions: [], userRemoteConfigs: [[url: 'https://github.com/Bezawada9999/test-project1.git']])
            }
        }
        stage('Build'){
            steps{
                sh : "mvn clean install package"
            }

        }
         stage('Deploy'){
            steps{
               
                deploy adapters: [tomcat9(credentialsId: 'tomcat2', path: '', url: 'http://54.252.226.106:8080')], contextPath: null, war: 'target/*.war' 
            }

        }
    }
}

