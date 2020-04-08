# Covid19Italia development runtime Dockerfile

This is a simple DockerFile for generating an image to quickly set-up your Jekyll development environment on Windows or MacOS.

## Building the image

in order to build the image move to the "Docker" directory in the root of the project and issue:

`$ docker build -t covid_dev .`

this will build the docker image with _covid_dev_ as tag name, of course, you can change the name to assign to the image.

## Running the image

in order to run the image, form the root of the project, type:

`$ docker run --rm -v ${PWD}:/opt -p 4000:4000 --name covid -it covid_dev`

where:
- --rm tells docker to remove the container after stopping it
- -v ${PWD}:/opt mounts the root of the project int he /opt folder of the container
- -p forward port 4000 of localhost to port 4000 of the container
- --name gives a name to the container
- -it in order to allow the in

the container will install Ruby dependncies in _vendor/bundle_ path and will run the serve command: _bundle exec jekyll serve_

you are now ready to start, type http://127.0.0.1:4000 in your browser to access the website