node('master') 
{
stage('ContinuousDownload')
{
    git credentialsId: '8bad2997-6fdf-4359-b276-a8e166e7ae88', url: 'https://github.com/medamshiva20/JavaProject.git'
}
stage('ContinuousBuild')
{
  sh 'mvn package'   
}
stage('ContinuousDeployment')
{
    sh 'scp /home/ubuntu/.jenkins/workspace/scppipeline1/webapp/target/webapp.war ubuntu@172.31.29.148:/var/lib/tomcat8/webapps/testapp2.war'
}
stage('ContinuousTesting')
{
    git credentialsId: '8bad2997-6fdf-4359-b276-a8e166e7ae88', url: 'https://github.com/medamshiva20/SeleniumTesting.git'
}
stage('ContinuousDelivery')
{
    sh 'scp /home/ubuntu/.jenkins/workspace/scppipeline1/webapp/target/webapp.war ubuntu@172.31.20.160:/var/lib/tomcat8/webapps/prodapp2.war'
}
}
