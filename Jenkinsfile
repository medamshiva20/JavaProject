node('master')
{
    stage('Continuous Download')
    {
        git credentialsId: '34d79418-82a6-4d03-a3a8-97cb5cf000d9', url: 'https://github.com/medamshiva20/JavaProject.git'
    }
    stage('Continuous Build')
    {
        sh 'mvn package'
    }
}
