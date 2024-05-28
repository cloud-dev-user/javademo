pipeline{
    agent { label 'aws-agent'}
    parameters {string defaultValue: 'master', name: 'branch_name'}
    stages {
        stage("Checkout from branch"){
            steps{
                git branch: '$branch_name', url: 'https://github.com/PrashantDJoshi/javademo.git'
            }
        }
        stage("Checkout"){
            steps{
                checkout scmGit(branches: [[name: '*/master']], extensions: [], userRemoteConfigs: [[url: 'https://github.com/cloud-dev-user/javademo.git']])
            }
        }
        
        stage("Build"){
            steps{
                sh 'mvn package'
            }
        }
        stage("Clean Workspace"){
           steps{
             cleanWs()
            }
        }
    }
}
