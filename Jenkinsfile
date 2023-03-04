pipeline
{
    agent any
    stages
    {
         stage('ContinuousTesting')
         {
             steps
             {
                 git credentialsId: '762fec62-9315-4086-a79c-03530a61770d', url: 'https://github.com/medamshiva20/SeleniumTesting.git'
                 sh 'java -jar /root/.jenkins/workspace/Declarativepipeline1/testing.jar'
             }
         }
         stage('ContinuousDelivery')
         {
             steps
             {
                 sh 'scp /root/.jenkins/workspace/Declarativepipeline1/webapp/target/webapp.war root@172.31.28.194:/var/lib/tomcat8/webapps/prodapp2.war'
             }
         }
        }
    }
