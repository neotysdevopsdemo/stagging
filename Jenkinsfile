
pipeline {
    agent {
        label 'master'
    }
    environment {
        VERSION="0.1"
    }
    stages {


        stage('Deploy to stagging namespace') {
            steps {
                sh "sed -i 's,VERSION_TO_REPLACE,${VERSION},'  $WORKSPACE/docker-compose.yml"
                sh 'docker-compose -f $WORKSPACE/docker-compose.yml up -d'

            }

        }


        stage('Mark artifact for staging namespace') {

            steps {
                // mark containers for production
                 ///   sh "docker tag ${_TAG_DEV} ${_TAG_STAGING}"
                  //  sh "docker push ${_TAG_STAGING}"

            }
        }

    }
}

