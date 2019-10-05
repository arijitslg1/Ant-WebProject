pipeline {
	agent any	
		stages
			{
			stage ('SCM Checkout')
					{	
						git 'https://github.com/arijitslg1/maven-project.git'
					}
			}
      {
	stage ('Build && SonarQube Analysis') 
		    {	
			  steps {
              withSonarQubeEnv('sonar')
						  {
					  withAnt(maven : 'LocalAnt') 
						  	{	
							  	sh 'ant clean package sonar:sonar'
							  }				
						  }		
					  }	
				}		
      }
}
