node('master')
{
stage('continousdownload')
{
   git 'https://github.com/vemula1616/Maven.git' 
}
stage('contnuousbuild')
{
      sh 'mvn package'
}
stage('continuousdeployment')
{
  sh 'scp /home/ubuntu/.jenkins/workspace/scriptedpipeline/webapp/target/webapp.war ubuntu@172.31.7.131:/var/lib/tomcat8/webapps/test.war'  
}
stage('continuoustesting')
{
   git 'https://github.com/vemula1616/FunctionalTesting.git'
   sh 'java -jar /home/ubuntu/.jenkins/workspace/scriptedpipeline/testing.jar'
}
stage('continuousdelivery')
{
  sh 'scp /home/ubuntu/.jenkins/workspace/scriptedpipeline/webapp/target/webapp.war ubuntu@172.31.9.140:/var/lib/tomcat8/webapps/prod.war'  

}
}
