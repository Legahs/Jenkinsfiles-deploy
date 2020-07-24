node
{
    
    
def mavenHome = tool name: "maven3.6.3"

properties([[$class: 'JiraProjectProperty'], buildDiscarder(logRotator(artifactDaysToKeepStr: '', artifactNumToKeepStr: '5', daysToKeepStr: '', numToKeepStr: '5')), pipelineTriggers([pollSCM('* * * * *')])])

stage('CheckoutCode')
{
  git branch: 'development', credentialsId: 'e2b1372b-49dd-439b-b6f9-ee65e49111fe', url: 'https://github.com/MithunTechnologiesDevOps/maven-web-application.git'
}

stage('Build')
{
sh "${mavenHome}/bin/mvn clean package"
}
/*
stage('ExecuteSonarQubeReport')
{
sh "${mavenHome}/bin/mvn sonar:sonar"
}

stage('UploadArtifactIntoNexus')
{
sh "${mavenHome}/bin/mvn deploy"
}

stage('DeployAppIntoTomcatServer')
{
sshagent(['d31ecc1f-5e11-4268-919e-31a8f360d829']) 
{
 sh "scp -o StrictHostKeyChecking=no target/maven-web-application.war ec2-user@13.234.232.145:/opt/apache-tomcat-9.0.37/webapps/"  
}

}

stage('SendEmailNotification')
{
emailext body: '''Build is over..

Regards,
Mithun Technologies,
9980923226''', subject: 'Build is over', to: 'devopstrainingblr'
}
*/
    
    
}


