pipeline {
    agent none

    stages {
        stage('Back-end Build') {
            agent {
                docker { image 'maven:3.8.1-adoptopenjdk-11' }
            }
            steps {
                dir('backend') {
                    sh 'mvn clean package -DskipTests'
                    // Stash backend jar to make it available to later stages
                    stash includes: 'target/*.jar', name: 'backend-jar'
                }
            }
        }

        stage('Front-end Build') {
            agent {
                docker { image 'node:16-alpine' }
            }
            steps {
                dir('frontend') {
                    sh 'npm install'
                    sh 'npm run build'
                    // Stash frontend build folder
                    stash includes: 'build/**', name: 'frontend-build'
                }
            }
        }

        stage('Integration (Dummy)') {
            agent any
            steps {
                // Unstash backend and frontend files
                dir('backend') { unstash 'backend-jar' }
                dir('frontend') { unstash 'frontend-build' }

                echo 'Backend and Frontend build artifacts are ready!'
                sh 'ls -R backend/target frontend/build'
            }
        }
    }

    post {
        always {
            echo "Pipeline completed."
        }
    }
}
