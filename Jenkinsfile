pipeline {
    agent any

    stages {
        stage('Checkout') {
            stage('Checkout') {
            steps {
            checkout([$class: 'GitSCM', branches: [[name: '*/dev']], extensions: [], userRemoteConfigs: [[url: 'https://github.com/BIG-INTERNET-DEVOPS-RESOURCES/myInfra2021Repo']]])   
            }
        }
    
        stage ("terraform init") {
            steps {
                sh ("terraform init -reconfigure") 
            }
        }
        
        stage ("validate") {
            steps {
                sh ('terraform validate') 
            }
        }

        stage (" Action") {
            steps {
                echo "Terraform action is --> ${action}"
                sh ('terraform ${action} --auto-approve') 
           }
        }
    }
}
    
