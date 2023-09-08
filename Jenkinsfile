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
			sh ' docker run -dit --net net-projet -p 27017:27017 --name container-db chetouiiftikhar/db:db '
                        sh ' docker run -dit --net net-projet -p 3080:3080 --name api-container chetouiiftikhar/api:api '
                        sh ' docker run -dit --net net-projet -p 3000:3000 --name ui-container chetouiiftikhar/ui:ui '

                      }}
                      
}
}
