pipeline {
    agent {
        label 'shrey-agent-1'
    }
    parameters { string defaultValue: 'master', name: 'branch_name' }
    stages {
        stage("checkout the code") {
            steps {
                git branch: "$branch_name", url: 'https://github.com/Shreyashi-Samaddar/javademo.git'
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
