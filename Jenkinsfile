node {
   def mvnHome
   stage('code checkout') { 
       git credentialsId: 'GitHub-ID', url: 'https://github.com/digitalorg/maven-examples'       
   }
   stage('build') {
       withMaven(jdk: 'java-8', maven: 'Maven') {
           sh 'mvn clean compile'
        }
      
   }
   stage('test') {
       withMaven(jdk: 'java-8', maven: 'Maven') {
           sh 'mvn test'
      }
      
   }
   stage('sonarqube analysis') {
       withMaven(jdk: 'java-8', maven: 'Maven') {
           sh 'mvn sonar:sonar -Dsonar.projectKey=Name -Dsonar.organization=digitalorg -Dsonar.host.url=https://sonarcloud.io -Dsonar.login=abbceafed96e54d46c1efe75f4bf3ae4d860c837'
      }
     
   }  
   stage('package') {
       withMaven(jdk: 'java-8', maven: 'Maven') {
           sh 'mvn package'
     }
      
   }
   stage('deploy to dev environment') {
      
   }
   stage('deploy to QA environment') {
      
   }
   stage('deploy to production environment') {
      
   }
}
