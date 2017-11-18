pipeline {
    agent any 

    stages {
        stage('Bundler') { 
            steps { 
                sh '''rbenv exec gem install bundler
                      rbenv exec bundle install --path=~/.bundle'''
            }
        }
        stage('Test') {
            steps {
                sh '''rbenv exec bundle exec rspec spec/ --format RspecJunitFormatter --out spec/rspec.xml '''
                junit 'spec/*.xml'
            }
        }
    }
}
