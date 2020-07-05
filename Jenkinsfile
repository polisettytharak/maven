node('master')
{
    stage('ContinuousDownload')
    {
        git 'https://github.com/polisettytharak/maven.git'
    }
    stage('ContinuousBuild')
    {
        sh label: '', script: 'mvn package'
    }
    stage('ContinuousDeployment')
    {
        sh label: '', script: 'scp /home/ubuntu/.jenkins/workspace/pipeline/webapp/target/webapp.war ubuntu@172.31.59.98:/var/lib/tomcat8/webapps/testapp.war'
    }
    stage('ContinuousTesting')
    {
       git 'https://github.com/polisettytharak/maven.git'
    }
	
    stage('ContinuousDelivery')
    {
        sh label: '', script: 'scp /home/ubuntu/.jenkins/workspace/pipeline/webapp/target/webapp.war ubuntu@172.31.60.23:/var/lib/tomcat8/webapps/prodapp.war'
    }
}