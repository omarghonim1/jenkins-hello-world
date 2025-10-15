pipeline {
    agent any 
    tools {
        // Install the Maven version configured as "M3" and add it to the path.
        jdk "JDK17"
        maven "M3911"
    }

    stages {
        stage( 'Echo Version'){
            steps{
                sh 'echo Print Maven Version'
                sh 'mvn -version'
            }
        }
        stage('Build') {
            steps{
                // Get a repo from git hub
               git branch: 'main', url: 'https://github.com/omarghonim1/jenkins-hello-world.git'
                
                // Run Maven package CMD
                sh "mvn clean package -DskipTests=true"
            }
        }
        stage('Unit Test'){
            steps {
                sh "mvn test"
            }
        }
        // stage('Build') {
        //     steps {
        //         // Run Maven on a Unix agent.
        //         sh "mvn -Dmaven.test.failure.ignore=true clean package"

        //         // To run Maven on a Windows agent, use
        //         // bat "mvn -Dmaven.test.failure.ignore=true clean package"
        //     }

        //     post {
        //         // If Maven was able to run the tests, even if some of the test
        //         // failed, record the test results and archive the jar file.
        //         success {
        //             junit '**/target/surefire-reports/TEST-*.xml'
        //             archiveArtifacts 'target/*.jar'
        //         }
        //     }
        // }
    }
}
