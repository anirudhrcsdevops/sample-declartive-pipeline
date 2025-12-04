pipeline {

    /******************************
     * STEP 1: Choose the agent 
     ******************************/
    agent any      
    // Meaning: Run this pipeline on ANY available Jenkins machine


    /******************************
     * STEP 2: Define variables 
     ******************************/
    environment {
        APP = "sample-declartive-pipeline"
    }


    /******************************
     * STEP 3: Pipeline settings
     ******************************/
    options {
        timestamps()                 // show timestamps in console
        disableConcurrentBuilds()    // stop multiple parallel runs
    }


    /******************************
     * STEP 4: Define all stages
     ******************************/
    stages {

        /********************
         * Stage 1: Checkout
         ********************/
        stage('Checkout') {
            steps {
                echo "Fetching source code..."
                git 'https://github.com/anirudhrcsdevops/sample-declartive-pipeline.git'x`
            }
        }

        /********************
         * Stage 2: Build
         ********************/
        stage('Build') {
            steps {
                echo "Building the POC application..."
                // Example:
                // sh 'mvn clean package'
            }
        }

        /********************
         * Stage 3: Test
         ********************/
        stage('Test') {
            steps {
                echo "Running POC tests..."
                // Example:
                // sh 'mvn test'
            }
        }

        /********************
         * Stage 4: Deploy
         ********************/
        stage('Deploy') {
            steps {
                echo "Deploying ${APP} (POC simulation)..."
                sh 'echo Deployment successful!'
            }
        }
    }


    /******************************
     * STEP 5: Post Actions
     ******************************/
    post {
        success {
            echo "POC Pipeline completed successfully ✔"
        }
        failure {
            echo "POC Pipeline failed ❌"
        }
        always {
            echo "Cleaning workspace..."
            cleanWs()
        }
    }
}
