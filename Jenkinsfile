pipeline
{
    agent any
    stages
    {
        stage('Continuous Download')
        {
            steps
            {
                git credentialsId: '8a56ad3e-3e55-4dfc-ba72-4bb533118b25', url: 'https://github.com/medamshiva20/JavaProject.git'
            }
        }
        stage('Continuous Build')
        {
            steps
            {
                sh 'mvn package'
            }
        }
        stage('Continuous Deployment')
        {
            steps
            {
                sh 'scp /home/ubuntu/.jenkins/workspace/dcp1/webapp/target/webapp.war ubuntu@172.31.21.96:/var/lib/tomcat8/webapps/dcptest.war'
            }
        }
        stage('Continuous Testing')
        {
            steps
            {
             git credentialsId: '8a56ad3e-3e55-4dfc-ba72-4bb533118b25', url: 'https://github.com/medamshiva20/SeleniumTesting.git'   
            }
        }
        stage('Continuous Delivery')
        {
            steps
            {
                sh 'scp /home/ubuntu/.jenkins/workspace/dcp1/webapp/target/webapp.war ubuntu@172.31.23.251:/var/lib/tomcat8/webapps/dcpprod.war'
            }
        }
    }
}
