
pipeline{
agent any
stages('CI CD Pipeline'){
  stage('Code Checkout'){
    steps{
        script{
                git credentialsId: 'sonarqube', url: 'https://github.com/sushma335/MavenBuild'
            }
        }
    }
  
  stage('Build'){
    steps{
        script{
            sh "mvn clean install -Dmaven.test.skip=true"
        }
    }  
  }
  stage('Test'){
    steps{
        script{
            sh "mvn clean org.jacoco:jacoco-maven-plugin:prepare-agent install -Pcoverage-per-test"
        }
    }  
  }
}
}
