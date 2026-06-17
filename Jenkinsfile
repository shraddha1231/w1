pipeline {
	agent any
	
	tools{
	  maven 'Maven'
	 }
	 
	 stages{
	 	stage('Checkout'){
			steps{	 	
	 		git branch : 'master' , url :'https://github.com/shraddha1231/w1.git'
	 	}
	 }
	 	stage('Build'){
			steps{	 	
	 		sh 'mvn clean package'
	 	}
	 }
	 	stage('Archive'){
			steps{	 	
	 		archiveArtifacts artifacts:'target/*.war',fingerprint:true
	 	}
	 }
	 	stage('Deploy'){
			steps{	 	
	 		sh 'ansible-playbook playbook.yml -i hosts.ini'
	 	}
	 }
	 }
	post{
		success{
			echo "buils"
		}
		failure{
			echo "fail"
			}
		}
}
