pipeline {
    agent { label 'rgarlando' }
    stages {
        stage('Build') {
            steps {
                script {
                    git (
                        branch: 'main', url: 'https://github.com/rgarlando23/node-webapp.git', credentialsId:'GithubUser' )
                    sh 'docker build . -t node-webapp/latest '
                    sh 'docker run -d -p 3000:80 node-webapp/latest'
                }
            }
        }
    }
}
