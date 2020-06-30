node('master')
{
   stage('ContinuousDownload')
   {
    git 'https://github.com/medamshiva20/Maven11.git'
   }
   stage('ContinuousBuild') 
   {
    sh label: '', script: 'mvn package'
   }
   stage('ContinuousDeployment') 
   {
   sh label: '', script: 'scp /home/ubuntu/.jenkins/workspace/ScriptedPipiline5/webapp/target/webapp.war ubuntu@172.31.21.197:/var/lib/tomcat8/webapps/TestingApp5.war'   
}
stage('ContinuousTesting')
{
  git 'https://github.com/medamshiva20/FunctionalTesting.git'
  sh label: '', script: 'java -jar /home/ubuntu/.jenkins/workspace/ScriptedPipiline5/testing.jar'
  
}
stage ('ContinuousDelivery')
{
    sh label: '', script: 'scp /home/ubuntu/.jenkins/workspace/ScriptedPipiline5/webapp/target/webapp.war ubuntu@172.31.17.160:/var/lib/tomcat8/webapps/ProdApp5.war'
}
}
