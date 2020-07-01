  pipeline
{
    agent any
    stages
    {
        stage('ContinuousDownload')
        {
            steps
            {
                script
                {
                   try
                   {
                       git 'https://github.com/intelliqittrainings/maven.git'
                   }
                   catch(Exception e1)
                   {
                       mail bcc: '', body: 'Jenkins is unable to download from remote github', cc: '', from: '', replyTo: '', subject: 'Download failed', to: 'gitadmin@outlook.com'
                       exit(1)
                   }
                }
            }
        }
         stage('ContinuousBuild')
        {
            steps
            {
                script
                {
                   try
                   {
                       sh label: '', script: 'mvn package'
                   }
                   catch(Exception e2)
                   {
                       mail bcc: '', body: 'Jenkins is unable to create an artifact from the code', cc: '', from: '', replyTo: '', subject: 'Build failed', to: 'developers@outlook.com'
                      exit(1)
                   }
                }
            }
}
 stage('ContinuousDeployment')
        {
            steps
            {
                script
                {
                   try
                   {
                    sh label: '', script: 'scp /home/ubuntu/.jenkins/workspace/MultibranchPipeline_master/webapp/target/webapp.war ubuntu@172.31.31.15:/var/lib/tomcat8/webapps/Mtestwebapp.war'
                   }
                   catch(Exception e3)
                   {
          mail bcc: '', body: 'Deploy the artifact into the testing server', cc: '', from: '', replyTo: '', subject: 'Deploy the artifact into the testing server', to: 'medamshiva20@gmail.com'
                       exit(1)
                   }
                }
            }

        }
}
}

