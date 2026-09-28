pipeline {
    agent any

    maven 'M3'

    stages{
        stage('github'){
            steps{
                git credentialsId: 'github_app', url: 'https://github.com/saranyaAWS/PROJECTTITLE.git'
            }
        }
        stage('build'){
            steps{
               sh 'mvn --version'
               echo "maven version sucessfully installed "
            }
        }

        stage('Test'){
            steps{
                sh 'mvn clean compile'
            }
        }
        stage('deploy'){
            steps{
                sh 'mvn test'
            }
        }
        stage ('run'){
            steps{
                sh 'mvn package'
            }
        }
        stage('runthe helloworld'){
            steps{
                sh 'mvn exec:java'
            }
        }
    }
    post{
        sucess{
            echo "java successfully run"
        }
        failure{
            echo "java failure"
        }
    }

}
