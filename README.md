# hello-ruby-on-rails

## Setting Up a New Ruby on Rails Project

1) Install Docker for Mac and start it.

2) Clone the repository.

2) `docker build -t rails-env -f Dockerfile.rails-env .`

3) `docker run -it -v [PATH_TO_APP]:/app rails-env rails new [NAME_OF_APP]`

## Running a Ruby on Rails Project

1) Copy the Dockerfile.rails-server to a Dockerfile in the root directory of your application.

2) Copy the docker-compose.yml file to the root directory of your application. Update the image to match the name of your app.

3) `docker-compose up -d --build`

4) Go to http://localhost:3000 and view Rails app running

## Other useful commands

- `docker-compose up [-d]`

- `docker-compose run --rm app rails c`

- `docker-compose run --rm app rake db:create db:migrate db:test:prepare`

- `docker-compose run --rm app rspec`

- `docker-compose run --rm -p 127.0.0.1:3000:3000 app`

## Notes

- Using the option [--rm] deletes the container right after it terminates, helping with cleanup.

- Using the option [-d] makes the server run in the background.

- Debugging with a tool like byebug will only work when using `docker-compose run`

## Adding an interactive terminal to `docker-compose up`

1) Add the following lines to our app service in `docker-compose.yml`

```
tty: true
stdin_open: true
```

2) `docker-compose up -d`

3) `docker-compose ps`

4) `docker attach [container]`

## Using just Docker instead of in combination with docker-compose

1) `docker build -t [NAME_OF_APP] .`

2) `docker run -p 3000:3000 -it [NAME_OF_APP]`
