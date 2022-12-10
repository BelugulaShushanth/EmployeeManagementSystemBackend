pipeline{
    agent any

    stages{
        stage('Pre BUild'){
            steps{
                sh 'echo ${env.JOB_NAME}'
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