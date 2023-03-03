node('master')
{
    stage('ContinuousDownlaod')
    {
        git credentialsId: '762fec62-9315-4086-a79c-03530a61770d', url: 'https://github.com/medamshiva20/JavaProject.git'
    }
    stage('ContinuousBuild')
    {
        sh 'mvn package'
    }
    stage('ContinuousDeployment')
    {
        sh 'scp /root/.jenkins/workspace/Scriptedpipeline1/webapp/target/webapp.war root@172.31.61.80:/var/lib/tomcat8/webapps/testapp.war'
    }
    stage('ContinuousTesting')
    {
        git credentialsId: '762fec62-9315-4086-a79c-03530a61770d', url: 'https://github.com/medamshiva20/SeleniumTesting.git'
        sh 'java -jar /root/.jenkins/workspace/Scriptedpipeline1/testing.jar'
    }
    stage('ContinuousDelivery')
    {
        sh label: 'master', script: 'scp /root/.jenkins/workspace/Scriptedpipeline1/webapp/target/webapp.war root@172.31.28.194:/var/lib/tomcat8/webapps/prodapp.war'
    }
}
