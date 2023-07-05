pipeline
{
    agent any
    stages
    {
        stage('Continuous Download')
        {
            steps
            {
                script
                {
                    try
                    {
                        git credentialsId: 'e5ea0a6a-2c38-4705-bc65-883fb8fb299c', url: 'https://github.com/medamshiva20/JavaProject.git'
                    }
                    catch(Exception e1)
                    {
                        mail bcc: '', body: 'Download the code from github', cc: '', from: '', replyTo: '', subject: '', to: 'sivadevops1014@gmail.com'
                        exit(1)
                    }
                }
            }
        }
        stage('Continuous Build')
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
                        mail bcc: '', body: 'Build the artifact from downloaded source code', cc: '', from: '', replyTo: '', subject: '', to: 'madamshiva20@gmail.com'
                        exit(1)
                    }
                }
            }
        }
        stage('Continuous Deployment')
        {
            steps
            {
                script
                {
                    try
                    {
                     sh 'scp /home/ubuntu/.jenkins/workspace/Declarativepipeline2/webapp/target/webapp.war ubuntu@172.31.4.211:/var/lib/tomcat9/webapps/testapp3.war'   
                    }
                    catch(Exception e3)
                    {
                        mail bcc: '', body: 'Deploy the artifact into testing servers', cc: '', from: '', replyTo: '', subject: '', to: 'medamshiva20@gmail.com'
                        exit(1)
                    }
                }
            }
        }
        stage('Continuous Testing')
        {
            steps
            {
                script
                {
                    try
                    {
                        git credentialsId: 'e5ea0a6a-2c38-4705-bc65-883fb8fb299c', url: 'https://github.com/medamshiva20/SeleniumTesting.git'
                    }
                    catch(Exception e4)
                    {
                        mail bcc: '', body: 'Run automation test scripts to test the application', cc: '', from: '', replyTo: '', subject: '', to: 'sivamedam21@gmail.com'
                        exit(1)
                    }
                }
            }
        }
        stage('Continuous Delivery')
        {
            steps
            {
                script
                {
                    try
                    {
                        sh 'scp /home/ubuntu/.jenkins/workspace/Declarativepipeline2/webapp/target/webapp.war ubuntu@172.31.5.183:/var/lib/tomcat9/webapps/prodapp3.war'
                    }
                    catch(Exception e5)
                    {
                        mail bcc: '', body: 'Delivery the appication into Prod environment', cc: '', from: '', replyTo: '', subject: '', to: 'sivamedam22@gmail.com'
                        exit(1)
                    }
                }
            }
        }
    }
}
