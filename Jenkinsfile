node{        
    stage('Git'){
        git branch: 'main', credentialsId: 'Srinivas-Git', url: 'https://github.com/krssrinivas7/vpc-ci.git'
    }
    stage('Maven'){
        bat "$M2_HOME/bin/mvn clean package"
    }
    stage('SonarQube'){
        bat "$M2_HOME/bin/mvn sonar:sonar"
    }
    stage('Nexus'){
       bat "$M2_HOME/bin/mvn clean deploy"
    }
    stage('Tomcat'){
        bat 'copy "C:\\JENKINSHOME\\workspace\\test\\target\\vprofile-v2.war" "C:\\Program Files\\Apache Software Foundation\\Tomcat 9.0\\webapps"\\vprofile-v2.war'
    }    
}