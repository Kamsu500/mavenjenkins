pipeline {
    agent { docker 'maven:3.9.3-eclipse-temurin-17' }
   
    stages {
        stage('Installation de maven') {
            steps {
                sh 'mvn clean install'
            }
        }

        stage('clean et Installation les dependances') {
            steps {
                sh 'mvn -v'
            }
        }
         stage('Execution des tests') {
            steps {
                sh 'mvn  test'
            }
        }
       
    }
     post{
            always{
                echo 'affichage des rapports'
            }
        }
}