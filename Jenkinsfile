pipeline {
agent any
environment{DOCKERHUB_CREDENTIALS=credentials('dockerhub')}
 stages {
        stage('Build') {
			steps{   
			
      sh ' docker build -t chetouiiftikhar/db:db db/ '
      sh 'docker build -t chetouiiftikhar/api:api bakend/ '
      sh 'docker build -t chetouiiftikhar/ui:ui frontend/'
            } 
            }
	  stage('login') {
			steps{   
			
			sh ' echo $DOCKERHUB_CREDENTIALS_PSW | docker login -u $DOCKERHUB_CREDENTIALS_USR --password-stdin '
                      } }
         stage('push') {
			steps{
			 sh ' docker push chetouiiftikhar/db:db  '
                         sh ' docker push chetouiiftikhar/api:api  '
                         sh ' docker push chetouiiftikhar/ui:ui  '

                      }}
          stage('run') {
			steps{
			sh 'docker-compose down'
		        sh 'docker-compose kill'
			sh 'docker-compose up -d'
			
                      }}
                      
}
}
