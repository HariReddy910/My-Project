currentBuild.displayName="Hospital-Mang-Syatem-#"+currentBuild.number
pipeline{
    agent any
 //   options {
   //   timeout(time: 1, unit: 'MINUTES') 
    //     }
 
    stages{
        stage("Checkout-SCM")
        {
            steps{
                cleanWs()
                checkout([$class: 'GitSCM',
                branches: [[name: '*/master']], 
                doGenerateSubmoduleConfigurations: false,
                extensions: [[$class: 'CleanBeforeCheckout']], 
                submoduleCfg: [], 
                userRemoteConfigs: [[credentialsId: 'github_credentials', 
                url: 'https://github.com/HariReddy910/My-Project.git']]])
                echo "Download finished form SCM"
            }
        }
      //  stage("Build")
      //  {
           // steps{
                //  withSonarQubeEnv('SonarQube') {
             //    sh label: '', script: 'mvn package sonar:sonar '
              //   echo "archeiving Artifacts" 
               //  archiveArtifacts '**/*.war'
                //  }     
         //   }
      //  }
        stage("Build"){
            steps{
                withSonarQubeEnv('SonarQube') {
                sh label: '', script: 'mvn packag sonar:sonar'
                archiveArtifacts '**/*.war'
            } 
            }}


       
       
      stage("Deployment-AppServer"){
            steps{
              echo "hi"
             sh label: '', script: 'scp /var/lib/jenkins/workspace/My-Project/webapp/target/webapp.war ubuntu@172.31.2.23:/opt/tomcat9/webapps/HSPMS.war'
           }
      }
       
           stage('uploading artifacts to Jfrog artfactory') {
           steps {
              script { 
                 def server = Artifactory.server 'Artifactory-1'
                 def uploadSpec = """{ 
                   "files": [{
                       "pattern": "**/*.war",
                       "target": "release"
    
                       
                    }]
                 }"""
                  server.upload(uploadSpec) 
     }     }    }  
    }
    
}
