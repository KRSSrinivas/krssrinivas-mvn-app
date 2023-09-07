//with variable & localhost Jenkins, Tomcat & Maven
node{
//Git Repository
stage('Source_Code'){
git branch: 'main', credentialsId: 'gmail', url: 'https://github.com/KRSSrinivas/krssrinivas-mvn-app.git'
}
//Maven
stage('Build'){
bat "$M2_HOME/bin/mvn clean package"
}
//Sonarqube
stage('Code_Quality'){
bat "$M2_HOME/bin/mvn sonar:sonar"
}
//Nexus
stage('Artifact_storage'){
bat "$M2_HOME/bin/mvn clean deploy"
}
//Tomcat
stage('Deploy'){
bat 'copy "C:\\JENKINSHOME\\workspace\\srinivas-w-task\\target\\KRS-maven-web-app.war" "C:\\Program Files\\Apache Software Foundation\\Tomcat 9.0\\webapps"\\KRS-maven-web-app.war'
}
}//node close
