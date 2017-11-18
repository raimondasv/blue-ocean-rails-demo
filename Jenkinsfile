pipeline {
    agent any 

    stages {
        stage('Bundler') { 
            steps { 
                sh '''rbenv exec gem install bundler
                      rbenv exec gem install rspec_junit_formatter
                      rbenv exec bundle install --path=~/.bundle'''
            }
        }
        stage('Test') {
            sh '''rbenv exec rspec --format RspecJunitFormatter --out spec/rspec.xml '''
            junit 'spec/*.xml'
        }
    }
}
