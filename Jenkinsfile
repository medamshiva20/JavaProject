node('master')
{
    stage('COntinuousDownload')
    {
        git credentialsId: 'Git', url: 'https://github.com/medamshiva20/JavaProject.git'
    }
    stage('ContinuousBuild')
    {
        sh label: '', script: 'mvn package'
    }
    stage('Continuous Deployment')
    {
        sh label: '', script: 'scp /home/ubuntu/.jenkins/workspace/scrp1/webapp/target/webapp.war ubuntu@172.31.82.50:/var/lib/tomcat8/webapps/sctestapp1.war'
    }
    stage('Continuous Testing')
    {
        git credentialsId: 'Git', url: 'https://github.com/medamshiva20/SeleniumTesting.git'
    }
    stage('Continuous Delivery')
    {
        sh label: '', script: 'scp /home/ubuntu/.jenkins/workspace/scrp1/webapp/target/webapp.war ubuntu@172.31.61.1:/var/lib/tomcat8/webapps/scprodapp1.war'
    }
}
