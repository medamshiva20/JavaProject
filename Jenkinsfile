node('master')
{
    stage('Continuous Download')
    {
        git 'https://github.com/medamshiva20/JavaProject.git'
    }
    stage('Continuous Build')
    {
        sh 'mvn package'
    }
}
