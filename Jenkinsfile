pipeline{
    agent any

    stages{
        stage('Pre Build'){
            steps{
                script{
                    env.BUILD_NUMBER = "Build: "+ env.BUILD_NUMBER
                }
                echo "JOB_NAME: ${env.JOB_NAME}"
                ech "BUILD_ID: ${env.BUILD_NUMBER}"
            }
        }
        stage('Compile & Build Stage'){
            steps{
                withMaven(maven: 'maven_3.8.6'){
                    sh 'mvn clean compile'
                }
            }

        }
        stage('Package Stage'){
            steps{
                  withMaven(maven: 'maven_3.8.6'){
                      sh 'mvn package'
                  }
             }

        }
        stage('Deploy Stage'){
              steps{
                    withMaven(maven: 'maven_3.8.6'){
                          sh 'echo deploy'
                    }
              }

        }
    }
}