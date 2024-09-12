pipeline{
    agent { docker 'maven:3.9.3-eclipse-temurin-17' }
        stages{
            stage('verifier maven'){
                steps{
                    sh 'mvn -v'
                }
            }
            stage('clean et installer les dependance'){
                
                steps{
                    withMaven {
                        sh 'mvn clean'
                    }
                }
            }
            stage('execution des tests'){
                
                steps{
                    withMaven {
                        sh 'mvn test'
                    }
                }

            }
        }
        post{
            always{
                sh 'echo "affichage du rapport"'
                junit "target/surefire-reports/**/*.xml"
            }
            
        }
    }