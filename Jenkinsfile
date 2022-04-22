pipeline{
    agent{
        label "node"
    }
    stages{
        stage("A"){
            steps{
                echo "========executing A========"
            }
            docker.image('maven:3.3.3-jdk-8').inside {
                git 'https://github.com/zogato/spring-jenkins-test'
                sh 'mvn -B clean test'
            }
        }
    }
    post{
        always{
            echo "========always========"
        }
        success{
            echo "========pipeline executed successfully ========"
        }
        failure{
            echo "========pipeline execution failed========"
        }
    }
}