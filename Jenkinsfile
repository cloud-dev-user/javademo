pipeline {
    agent {
        label 'shrey-agent-1'
    }
    stages{
        stage("checkout the code") {
            steps {
                checkout scmGit(branches: [[name: '*/master']], extensions: [], userRemoteConfigs: [[url: 'https://github.com/cloud-dev-user/java-war-project.git/']])
            }
        }
        stage("build") {
            steps {
                sh 'mvn package'   
            }
        }
        stage("Clean workspace") {
            steps {
                cleanWs()
            }
        }
    }
}
