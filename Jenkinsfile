pipeline{
  agent any;
  options { 
    timestamps()
    buildDiscarder(logRotator(numToKeepStr: '10')) 
   }
  tools {
        maven 'maven19' 
    }
 triggers {
        cron('* * * * *')
    }
parameters {
        string(name: 'BRANCH', defaultValue: 'future', description: 'Please specify the branch')

        text(name: 'BIOGRAPHY', defaultValue: '', description: 'Enter some information about the person')

        booleanParam(name: 'TOGGLE', defaultValue: true, description: 'Toggle this value')

        choice(name: 'CHOICE', choices: ['One', 'Two', 'Three'], description: 'Pick something')

        password(name: 'PASSWORD', defaultValue: 'SECRET', description: 'Enter a password')
    }
  stages{
	stage('build'){
        when { branch 'master' }
	  steps{
	   sh 'mvn -f $WORKSPACE/ATD_Multi-Insurance-Services/pom.xml clean package'
	  }
    }
	}
}
