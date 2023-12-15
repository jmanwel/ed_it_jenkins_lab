pipeline {
 agent any
 environment{
 	DOCKERHUB_CREDENCIALS = credentials ('7112fbd5-ca4b-4f53-810b-ac8fe1d5b142')
 	RepoDockerHub = 'jmanwel'
 	NameContainer = 'challenge_melli'
 }
 stages {
 	stage('Build'){
 		steps{
 			sh "docker build -t  ${env.RepoDockerHub}/${env.NameContainer}:${env.BUILD_NUMBER} ."
 		}
 	}
 }
 stage('Login to Dockerhub'){
 	steps{
 	sh "echo $DOCKERHUB_CREDENCIALS_PSW | docker login -u $DOCKERHUB_CREDENCIALS_USR --password-stdin "
 	}
 }
 stage('Push image to Dockerhub'){
 	steps{
 		sh "docker push ${env.RepoDockerHub}/${env.NameContainer}:${env.BUILD_NUMBER} "
 	}
 }
 
}
