node('master')
{
    stage('Continuous Download')
    {
    // Downloading the code
    git credentialsId: '8a56ad3e-3e55-4dfc-ba72-4bb533118b25', url: 'https://github.com/medamshiva20/JavaProject.git'
    }
    stage('Continuous Build')
    {
        // Build the source code
        sh 'mvn package'
    }
    stage('Continuous Deployment')
    {
        // Deploy the artifact into tomcat server
        sh 'scp /home/ubuntu/.jenkins/workspace/scp1/webapp/target/webapp.war ubuntu@172.31.21.96:/var/lib/tomcat8/webapps/scptest.war'
    }
    stage('Continuous Testing')
    {
        // Test the application
        git credentialsId: '8a56ad3e-3e55-4dfc-ba72-4bb533118b25', url: 'https://github.com/medamshiva20/SeleniumTesting.git'
    }
    stage('Continuous Delivery')
    {
        // Deliver the application into PROD environment
        sh 'scp /home/ubuntu/.jenkins/workspace/scp1/webapp/target/webapp.war ubuntu@172.31.23.251:/var/lib/tomcat8/webapps/scpprod.war'
    }
}
