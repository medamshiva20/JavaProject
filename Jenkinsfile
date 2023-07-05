node('master')
{
    stage('Continuous Download')
    {
        git 'https://github.com/medamshiva20/JavaProject.git'
    }
    stage('Continuous Build')
    {
        sh 'mvn package'
    }
    stage('Continuous Deployment')
    {
        sh 'scp /home/ubuntu/.jenkins/workspace/Scp-pipeline1/webapp/target/webapp.war ubuntu@172.31.4.211:/var/lib/tomcat9/webapps/testapp1.war'
    }
    stage('COntinuous Testing')
    {
        git 'https://github.com/medamshiva20/SeleniumTesting.git'
    }
    stage('Continuous Delivery')
    {
        sh 'scp /home/ubuntu/.jenkins/workspace/Scp-pipeline1/webapp/target/webapp.war ubuntu@172.31.5.183:/var/lib/tomcat9/webapps/prodapp1.war'
    }
}
