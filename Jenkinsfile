pipeline {
    agent any
   
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