node('master')
{
    stage('Continuous Download')
    {
        git credentialsId: '34d79418-82a6-4d03-a3a8-97cb5cf000d9', url: 'https://github.com/medamshiva20/JavaProject.git'
    }
    stage('Continuous Build')
    {
        sh 'mvn package'
    }
    stage('COntinuous Deployment')
    {
        sh 'scp /home/ubuntu/.jenkins/workspace/scpp1/webapp/target/webapp.war ubuntu@172.31.11.13:/var/lib/tomcat8/webapps/TestApp1.war'
    }
    stage('Continuous Testing')
    {
        git credentialsId: '34d79418-82a6-4d03-a3a8-97cb5cf000d9', url: 'https://github.com/medamshiva20/SeleniumTesting.git'
    }
    stage('Continuous Delivery')
    {
        sh 'scp /home/ubuntu/.jenkins/workspace/scpp1/webapp/target/webapp.war ubuntu@172.31.13.43:/var/lib/tomcat8/webapps/ProdApp1.war'
    }
}
