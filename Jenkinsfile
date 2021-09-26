node('Node1') 
{
 def mavenHome = tool name: "maven3.8.2"  
 
 echo "Jenkins Home ${env.JENKINS_HOME}"
 echo "Jenkins Url ${env.JENKINS_URL}"
 
 properties([buildDiscarder(logRotator(artifactDaysToKeepStr: '', artifactNumToKeepStr: '', daysToKeepStr: '4', numToKeepStr: '4')), [$class: 'JobLocalConfiguration', changeReasonComment: ''], pipelineTriggers([pollSCM('* * * * *')])])
 stage ('git checkout')
 {
  git credentialsId: '1a51840c-689d-4fa7-a36b-b3d428eedf3d', url: 'https://github.com/anilredd/-maven-web-application.git'   
 }
 stage ('Build package')
 {
 sh "${mavenHome}/bin/mvn clean package"     
 }
}
