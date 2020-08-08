pipeline{
    environment {
        registry ='rajanandkumar/petclinic'
        registrycredential= 'docker_hub_rajanand29'
        dockerimage=''
agent any
stages{
    stage ('Build') {
      steps{
        echo "Building Project"
         sh './mvnw package'
      }
    }
    stage ('Archive') {
      steps{
        echo "Archiving Project"
       archiveArtifacts artifacts: '**/*.jar', followSymlinks: false
      }
    }
     stage ('Build Docker Image') {
      steps{
        echo "Building Docker Image"
          scripts{
              dockerimage=docker.build registry + ":$BUILD_NUMBER"
          }       
      }
    }
     stage ('Push Docker Image') {
      steps{
        echo "Docker Image Pushing"
       
      }
    }
    stage ('Deploy to Dev') {
      steps{
        echo "Deploy to Dev Environment"
       
      }
    }
  }

}
