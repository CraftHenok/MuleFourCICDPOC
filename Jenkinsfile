pipeline{
 agent any

 stages {
 	stage ('Build'){
 		steps {
 			withMaven(maven:'maven'){
 		                sh 'mvn -f mulesoftfourcicdpoc/pom.xml clean install'
 			}
 		}
 	}
 	stage ('Deploy'){
 		steps {
 			withMaven(maven:'maven'){
 				sh 'mvn -f mulesoftfourcicdpoc/pom.xml package deploy  -Dusername=$ANYPOINT_USR -Dpassword=$ANYPOINT_PSW -Denvironment=Development -DmuleDeploy'
 			}
 		}
 	}
 }

}