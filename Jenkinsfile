pipeline{
    agent any
    tools{
        maven 'Maven'
    }
    stages{
        stage("SCM Checkout"){
            steps{
            git 'https://github.com/kiranbuddi/java-hello-world-with-maven.git'
            }
        }
        
        stage("Sonar Scan"){
            steps{
                withSonarQubeEnv('sonarqube') {
                sh 'mvn sonar:sonar'
                    }
            }
        }
        
        stage("Maven Build"){
            steps{
                sh 'mvn clean package'
            }
        }
    }
}
