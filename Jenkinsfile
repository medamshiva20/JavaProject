node('master')
{
    stage('COntinuousDownload')
    {
        git credentialsId: 'Git', url: 'https://github.com/medamshiva20/JavaProject.git'
    }
    stage('ContinuousBuild')
    {
        sh label: '', script: 'mvn package'
    }
}
