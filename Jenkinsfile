node('master')
{
    stage('ContinuousDownload')
    {
        git 'https://github.com/medamshiva20/JavaProject.git'
    }
    stage('ContinuosBuild')
    {
        sh label: '', script: 'mvn package'
    }
    stage('ContinuousDeployment')
    {
        sh label: '', script: 'scp /home/ubuntu/.jenkins/workspace/scriptedpipeline1/webapp/target/webapp.war ubuntu@172.31.60.100:/var/lib/tomcat8/webapps/sapp1.war'
    }
    stage('ContinuousTesting')
    {
        git 'https://github.com/medamshiva20/FunctionalTesting.git'
        sh label: '', script: 'java -jar /home/ubuntu/.jenkins/workspace/scriptedpipeline1/testing.jar'
    }
    stage('ContinuousDelivery')
    {
        sh label: '', script: 'scp /home/ubuntu/.jenkins/workspace/scriptedpipeline1/webapp/target/webapp.war ubuntu@172.31.62.253:/var/lib/tomcat8/webapps/papp1.war'
    }
}
