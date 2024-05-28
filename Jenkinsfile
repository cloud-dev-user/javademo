pipeline {
         agent { label "agent1" } 
	 parameters { string defaultValue: 'master', name: 'branch_name' }
		 stages{ 
		          stage(" checkout code " ){
				  steps{
					git branch: "$branch_name", url: 'https://github.com/cloud-dev-user/javademo.git'
				  }
			  }
		         stage("Build package"){
			   steps{
			       sh " mvn package" 
				   }
				}
			   stage ("build notification"){
			   steps{
			        echo " this build is completed " 
					}
			    }	 
		 }
  post{
    always{
           cleanWs()
    }
  }
}
