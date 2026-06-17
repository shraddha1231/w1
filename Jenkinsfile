pipeline {
	agent any
	
	tools{
	  maven 'Maven'
	 }
	 
	 stages{
	 	stage('Checkout'){
			steps{	 	
	 		git branch : 'master' , url : ' '
	 	}
	 }
	 	stage('Build'){
			steps{	 	
	 		sh 'mavn clean package'
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
