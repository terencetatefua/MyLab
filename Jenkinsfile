pipeline{
    //Directives
    agent any
    tools {
        maven 'maven'     
    } 
    
    stages {
        // Specify various stage with in stages

        // stage 1. Build
        stage ('Build'){
            steps {
                sh 'mvn clean install package'
            }
        }

        // Stage2 : Testing
        stage ('Test'){
            steps {
                echo ' testing......'

            }
        }
        
         //stage3 : publish the artifacts to nexus
        stage ('Publish to Nexus'){
            steps {
                nexusArtifactUploader artifacts: [[artifactId: 'VinayDevOpsLab', classifier: '', file: 'target/VinayDevOpsLab-0.0.4-SNAPSHOT.war', type: 'war']], credentialsId: '43c02c68-b437-4e2d-8b92-8fcfda0799d5', groupId: 'com.vinaysdevopslab', nexusUrl: '172.20.10.172:8081', nexusVersion: 'nexus3', protocol: 'http', repository: 'TerenceDevopsLab-SNAPSHOT', version: '0.0.4-SNAPSHOT'
            }    
        }   
        // Stage3 : Deploying
        stage ('deploying'){
            steps {
                echo ' deploying......'

            }
       }
   
    }
    
  }
