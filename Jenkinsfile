node{
    
    properties([buildDiscarder(logRotator(artifactDaysToKeepStr: '', artifactNumToKeepStr: '', daysToKeepStr: '', numToKeepStr: '5')), [$class: 'JobLocalConfiguration', changeReasonComment: ''], 

pipelineTriggers([pollSCM('* * * * *')])])
    
    def mavenHome = tool name: "maven3.8.3"

stage('CheckoutCode'){

git branch: 'development', credentialsId: '7fcb22e2-9c7e-47e4-959d-e9cb418d62bf', url: 
'https://github.com/Shashi2994/maven-web-application.git'
}

stage('Build'){
sh "${mavenHome}/bin/mvn clean package"
}

 /*
stage('ExecuteSonarQubeReport'){
sh "${mavenHome}/bin/mvn sonar:sonar"
}

stage('UploadArtifactIntoNexusRepo'){
sh "${mavenHome}/bin/mvn deploy"
}

stage('DeployAppIntoTomcatServer')
{
sshagent(['23ce0cb8-12ad-4ada-9a04-1adbfed17146']) {
 sh "scp -o  StrictHostKeyChecking=no target/maven-web-application.war ec2-user@52.66.124.76:/opt/apache-tomcat-9.0.65/webapps/"
}

}
*/
}
