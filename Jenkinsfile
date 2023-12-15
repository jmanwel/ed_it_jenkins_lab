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
}
