pipeline
{
    agent any
    stages
    {
        stage('ContinuousDownload')
        {
            steps
            {
              git 'https://github.com/medamshiva20/JavaProject.git'  
            } 
        }
        stage('ContinuousBuild')
        {
            steps
            {
                sh 'mvn package'
            }
         }
         stage('ContinuousDeployment')
         {
             steps
             {
                sh 'scp /root/.jenkins/workspace/Multibranchpipeline_master/webapp/target/webapp.war root@172.31.61.80:/var/lib/tomcat8/webapps/testapp2.war'   
             }
         }
        }
    }
