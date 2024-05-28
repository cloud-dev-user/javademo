pipeline{
       agent {
          label 'agnet123'
        }

        stages {
            stage("checkout the code"){
                steps{
                    checkout scmGit(branches: [[name: '*/master']], extensions: [], userRemoteConfigs: 
                    [[url: 'https://github.com/sukamb/javademo.git']])
                }
            }
            stage("build the job"){
                steps{
                    sh 'mvn package'
                }
            }
        }
        post{
            always {
                cleanWs()
            }
        }
}
