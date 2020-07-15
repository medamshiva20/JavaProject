pipeline
{
    agent any
    stages
    {
        stage('ContinuousDownload_Loans')
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
        stage('ContinuousBiuld_Loans')
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
        }
    }
