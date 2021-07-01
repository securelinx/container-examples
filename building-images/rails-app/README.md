This example uses the opensuse/leap image to build an image to run an existing example rails application.

To build use:

    docker build -t rails-app .

And to run:

    docker run -p 3000:3000 --name my-rails-app rails-app

Or, to start with a volume defined for the db storage

    docker run -p 3000:3000 --name my-rails-app -v rails-vol:/var/db rails-app

To run a shell inside the running container use

    docker exec -it my-rails-app /bin/bash
