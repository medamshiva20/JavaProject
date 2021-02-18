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
        sh 'scp /home/ubuntu/.jenkins/workspace/scp1/webapp/target/webapp.war ubuntu@172.31.31.184:/var/lib/tomcat8/webapps/TestApp1.war'
    }
}
