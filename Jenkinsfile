pipeline{
  agent any;
  options { 
    timestamps()
    buildDiscarder(logRotator(numToKeepStr: '10')) 
   }
  tools {
        maven 'maven19' 
    }
  stages{
	stage('build'){
     
	  steps{
	   sh 'mvn -f $WORKSPACE/ATD_Multi-Insurance-Services/pom.xml clean package'
	  }
    }
	}
}
