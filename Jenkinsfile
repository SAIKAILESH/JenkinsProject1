pipeline
{
    agent any
    stages
    {
        stage("contDownload")
        {
            steps
            {
                git branch: 'main', url: 'https://github.com/SAIKAILESH/JenkinsProject1.git'
            }
        }
        stage("contBuild")
        {
            steps
            {
                sh 'mvn package'
            }
        }
        stage("contDeploy")
        {
            steps
            {
                deploy adapters: [tomcat9(credentialsId: 'b88f88d8-70ab-4e49-91d1-8e10673f8667', path: '', url: 'http://172.31.83.97:8080')], contextPath: 'test', war: '**/*.war'
            }
        }
    }
}