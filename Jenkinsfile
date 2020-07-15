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
                        git 'https://github.com/medamshiva20/JavaProject.git'
                    }
                    catch (Exception e1)
                    {
                        mail bcc: '', body: 'Continuous Download the code ', cc: '', from: '', replyTo: '', subject: 'Download the code', to: 'madamshiva20@gmail.com '
                        exit(1)
                    }
                }
            }
        }
        stage('ContinuousBiuld')
        {
            steps
            {
                script
                {
                    try
                    {
                        sh label: '', script: 'mvn package'
                    }
                    catch (Exception e2)
                    {
                        mail bcc: '', body: 'ContinuousBuild the code ', cc: '', from: '', replyTo: '', subject: 'Build the code', to: 'medamshiva20@gmail.com '
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
                        sh label: '', script: 'scp /home/ubuntu/.jenkins/workspace/Decpipeline130/webapp/target/webapp.war ubuntu@172.31.25.211:/var/lib/tomcat8/webapps/dtestapp130.war'
                    }
                    catch (Exception e3)
                    {
                        mail bcc: '', body: 'Continuous Deploy the code ', cc: '', from: '', replyTo: '', subject: 'Deploy the code', to: 'deployment@outlook.com'
                        exit(1)
                    }
                }
            }
        }
        stage('ContinuousTesting')
        {
            steps
            {
                script
                {
                    try
                    {
                        git 'https://github.com/medamshiva20/FunctionalTesting.git'
                        sh label: '', script: 'java -jar /home/ubuntu/.jenkins/workspace/Decpipeline130/testing.jar'
                    }
                    catch (Exception e4)
                    {
                        mail bcc: '', body: 'Continuous Testing the code ', cc: '', from: '', replyTo: '', subject: 'Testing the code', to: 'testing@outlook.com'
                        exit(1)
                    }
                }
            }
        }
        stage('ContinuousDelivery')
        {
            steps
            {
                script
                {
                    try
                    {
                        sh label: '', script: 'scp /home/ubuntu/.jenkins/workspace/Decpipeline130/webapp/target/webapp.war ubuntu@172.31.26.255:/var/lib/tomcat8/webapps/dprodapp130.war'
                    }
                    catch (Exception e5)
                    {
                        mail bcc: '', body: 'Continuous Delivery the code ', cc: '', from: '', replyTo: '', subject: 'Delivery the code', to: 'delivery@outlook.com'
                        exit(1)
                    }
                }
            }
        }
    }
}
