node('master')
{
    stage('ContinuousDownload') 
    {
    git credentialsId: '98f5dfcf-7dcb-4b16-bc9a-55a631035991', url: 'https://github.com/medamshiva20/JavaProject.git'
    }
   stage('ContinuousBuild')
   {
       sh 'mvn package'
   }
   stage('ContinuousDeployment')
   {
       sh 'scp /home/ubuntu/.jenkins/workspace/scp1/webapp/target/webapp.war ubuntu@172.31.8.92:/var/lib/tomcat8/webapps/testapp1.war'
   }
   stage('ContinuousTesting')
   {
       git credentialsId: '98f5dfcf-7dcb-4b16-bc9a-55a631035991', url: 'https://github.com/medamshiva20/SeleniumTesting.git'
   }
   stage('ContinuousDelivery')
   {
       sh 'scp /home/ubuntu/.jenkins/workspace/scp1/webapp/target/webapp.war ubuntu@172.31.3.86:/var/lib/tomcat8/webapps/prodapp1.war'
   }
}
