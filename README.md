# [Ruby on Rails App on Heroku](https://i18n-heroku-app.herokuapp.com/) [![Build Status](https://travis-ci.org/simplonco/rails-i18n-heroku.svg?branch=master)](https://travis-ci.org/simplonco/rails-i18n-heroku)

## Steps to get the application up and running:

* Create an app
```
rails new "name_the_app"
cd "name_the_app"
```
* Generate a controller
```
rails generate controller welcome index
```
* Edit your index in  app/views/welcome/index.html.erb
* Edit config/routes.rb: 
```
root 'welcome#index'
```
* Launch the app
```
rails server
```

## Setup your app for Heroku

Use the PostgreSQL 
(we need to add the pg gem in the production environment to allow Rails to talk to Postgres)
* Edit your Gemfile
```
group :development do
gem 'sqlite3'
end 

group :production do
gem 'pg', '0.15.1'
gem 'rails_12factor', '0.0.2'
end}

bundle install
```
* Install [Heroku Toolbelt](https://toolbelt.heroku.com/)
```
heroku login
cd ~/rails_projects/name_of_app
$ heroku create
```
If you have any problems with the public key, try:
```
heroku keys:add ~/.ssh/id_rsa.pub
```

## Heroku Deployment
```
git push heroku master
```

## Configuration
```
heroku open
heroku rename "name_your_app_on_heroku"
```

## To read more

* [Heroku Dev Center](https://devcenter.heroku.com)
