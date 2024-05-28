pipeline{
       agent {
          label 'agnet123'
        }

       parameters { string defaultValue: 'master', name:'branch_name'}
       stages {
              stage("Checkout code") {
              steps { 
                     git branch: "$branch_name", url:'https://github.com/sukamb/javademo.git'
                 }
              }
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
