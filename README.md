# hello-ruby-on-rails

## Setting Up a New Ruby on Rails Project

1) Install Docker for Mac and start it

2) Clone the repository

2) `docker build -t rails-env -f Dockerfile.rails-env .`

3) `docker run -it -v [PATH_TO_APP]:/app rails-env rails new [NAME_OF_APP]`

## Running a Ruby on Rails Project

1) Copy the Dockerfile.rails-server to a Dockerfile in the root directory of your application

2) `docker build -t [NAME_OF_APP] .`

3) `docker run -p 3000:3000 -it [NAME_OF_APP]`
