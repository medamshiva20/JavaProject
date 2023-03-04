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
=======
        stage('ContinuousDownload_Loans')
        {
            steps
            {
                script
                {
                    try
                    {
                        git credentialsId: '8bad2997-6fdf-4359-b276-a8e166e7ae88', url: 'https://github.com/medamshiva20/JavaProject.git'
                    }
                    catch(Exception e1)
                    {
                        mail bcc: '', body: '', cc: '', from: '', replyTo: '', subject: 'If download failed sent mail', to: 'madamshiva20@gmail.com'
                        exit(1)
                    }
                }
            }
			}
        stage('ContinuousBuild_Loans')
        {
            steps
            {
                script
                {
                    try
                    {
                       sh 'mvn package' 
                    }
                    catch(Exception e2)
                    {
                        mail bcc: '', body: '', cc: '', from: '', replyTo: '', subject: 'If build fail sent mail', to: 'medamshiva20@gmail.com'
                        exit(1)
                    }
                }
            }
        }
        stage('ContinuousDeployment_Loans')
        {
            steps
            {
                script
                {
                    try
                    {
                      sh 'scp /home/ubuntu/.jenkins/workspace/dcpipeline1/webapp/target/webapp.war ubuntu@172.31.29.148:/var/lib/tomcat8/webapps/dtestapp2.war'   
                    }
                    catch(Exception e3)
                    {
                        mail bcc: '', body: '', cc: '', from: '', replyTo: '', subject: 'If build fail sent mail', to: 'medamsiva874@gmail.com'
                        exit(1)
                    }
                }
            }
        }
        stage('ContinuousTesting_Loans')
        {
                steps
                {
				script
				{
                    try
                    {
                      git credentialsId: '8bad2997-6fdf-4359-b276-a8e166e7ae88', url: 'https://github.com/medamshiva20/SeleniumTesting.git'
                      sh 'java -jar /home/ubuntu/.jenkins/workspace/dcpipeline1/testing.jar'   
                    }
                    catch(Exception e4)
                    {
                      mail bcc: '', body: '', cc: '', from: '', replyTo: '', subject: 'If testing fail sent mail', to: 'sivareddy8583@gmail.com'
                      exit(1)
                    }
				}
                }
            }
 stage('ContinuousDelivery_Loans')
 {
 steps
 {
   script
   {
   try
   {
   sh 'scp /home/ubuntu/.jenkins/workspace/dcpipeline1/webapp/target/webapp.war ubuntu@172.31.20.160:/var/lib/tomcat8/webapps/dprodapp2.war'
 }
 catch(Exception e5)
 {
 mail bcc: '', body: '', cc: '', from: '', replyTo: '', subject: 'If testing fail sent mail', to: 'sivareddy8583@gmail.com'
 exit(1)
}
}
}
}
}
}
>>>>>>> 528bcaa8c7a319b9ada72c786eec244cde9df2b6
