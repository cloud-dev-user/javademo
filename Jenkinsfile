pipeline {
         agent any 
		 stages{ 
		 
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
