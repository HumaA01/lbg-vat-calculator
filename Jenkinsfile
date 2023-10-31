pipeline{
    agent any

    stages{
        stage('Checkout') {
            steps{
                git branch: 'main', url: 'https://github.com/HumaA01/lbg-vat-calculator.git'
            
            }
        }
        stage('SonarQube Analysis') {
            environment {
                scannerHome = tool 'somarqube'
            }
            steps{
                withSonarQubeEnv('sonar-qube-huma'){
                    sh "${scannerHome}/bin/sonar-scanner"
                }
            }
        }
    }
}