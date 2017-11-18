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
            steps {
                sh '''rbenv exec rspec spec/'''
                junit 'spec/*.xml'
            }
        }
    }
}
