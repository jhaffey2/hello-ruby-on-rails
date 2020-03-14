# hello-ruby-on-rails

## Setting Up a New Ruby on Rails Project

1) Clone the repository

2) Install Docker for Mac and start it

2) `docker build -t rails-new -f Dockerfile.rails-new .`

3) `docker run -it -v [PATH_TO_APP]:/app rails-new rails new --skip-bundle --skip-webpack-install [NAME_OF_APP]`
