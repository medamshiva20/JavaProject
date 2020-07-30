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

                    catch(Exception e1)

                    {

                        mail bcc: '', body: 'Download the code from git hub', cc: '', from: '', replyTo: '', subject: 'Download the code', to: 'gitadmin@outlook.com'

                        exit(1)

                    }

                }

            }

        }
	}
	}
