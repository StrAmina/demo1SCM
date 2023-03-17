CODE_CHANGES = getGitChanges()
pipeline {
    agent any
    environment{
        NEW_VERSION = '1.3.0'
        SERVER_CREDENTIALS = credentials('')
    }    

    stages {
        stage('Hello') {
            steps {
                echo 'Hello World'
            }
        }
         stage('build') {
            steps {
                echo 'building'
                echo "building version ${NEW_VERSION}"
            }
        }
         stage('deploy') {
            steps {
                echo 'deploying'
            }
        }
         stage('test') {
             when{
                 expression{
                     BRANCH_NAME == 'main'|| BRANCH_NAME == 'dev'&& CODE_CHANGES == true
                 }
             }   
            steps {
                echo 'testing'
            }
        }
    }
}
