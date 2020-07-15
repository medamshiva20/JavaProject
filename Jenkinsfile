node('master')
{
    stage('ContinuousDownload_master')
    {
        git 'https://github.com/medamshiva20/JavaProject.git'
    }
    stage('ContinuousBuild_master')
    {
        sh label: '', script: 'mvn package'
    }
    stage('ContinuousDeployment_master')
    {
        sh label: '', script: 'scp /home/ubuntu/.jenkins/workspace/scriptedpipeline120/webapp/target/webapp.war ubuntu@172.31.25.211:/var/lib/tomcat8/webapps/stestapp120.war'
    }
    stage('ContinuousTesting_master')
    {
        git 'https://github.com/medamshiva20/FunctionalTesting.git'
        sh label: '', script: 'java -jar /home/ubuntu/.jenkins/workspace/scriptedpipeline120/testing.jar'
    }
    stage('ContinuousDelivery_master')
    {
        sh label: '', script: 'scp /home/ubuntu/.jenkins/workspace/scriptedpipeline120/webapp/target/webapp.war ubuntu@172.31.26.255:/var/lib/tomcat8/webapps/sprodapp120.war'
    }
}
