node('master')
{
    stage('ContinuousDownload')
    {
        git 'https://github.com/medamshiva20/JavaProject.git'
    }
    stage('ContinuousBuild')
    {
        sh label: '', script: 'mvn package'
    }
    stage('ContinuousDeployment')
    {
        sh label: '', script: 'scp /home/ubuntu/.jenkins/workspace/scriptedpipeline120/webapp/target/webapp.war ubuntu@172.31.25.211:/var/lib/tomcat8/webapps/stestapp120.war'
    }
    stage('ContinuousTesting')
    {
        git 'https://github.com/medamshiva20/FunctionalTesting.git'
        sh label: '', script: 'java -jar /home/ubuntu/.jenkins/workspace/scriptedpipeline120/testing.jar'
    }
    stage('ContinuousDelivery')
    {
        sh label: '', script: 'scp /home/ubuntu/.jenkins/workspace/scriptedpipeline120/webapp/target/webapp.war ubuntu@172.31.26.255:/var/lib/tomcat8/webapps/sprodapp120.war'
    }
}
