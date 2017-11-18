pipeline {
    agent any 

    stages {
        stage('Bundler') { 
            steps { 
                sh '''rbenv exec gem install bundler
rbenv exec bundle install --path=~/.bundle'''
            }
        }
    }
}
