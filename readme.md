# Apache, PHP, MySQL and Redis with Docker.

## Build an image
Build an imahe from `Dockerfile` and target current directory `.`
``` bash
docker build --file .docker/Dockerfile -t php-docker .
```

## Runnig image with apache
After building an image, it is time to run it and map the port `8080` from host(our computer) to port `80` in docker. `php-docker` at the end of command is the name of image we created in the previous step.

``` bash
docker run --rm -p 8080:80 php-docker
```

### with a fancy name
Add a custome name to the image when it is running with `--name xxx`
``` bash
docker run --name php-docker --rm -p 8080:80 php-docker
```

Finally, you can see the application in browser in this URL: `http://localhost:8080`

 - If you want to see the running `php-docker` container in the Docker CLI, open a new terminal window and run `docker ps`

## More
You will need to build the image on a new machine before running it and when you make changes to the `Dockerfile` or `Vhost`. You can also run `docker-compose build` to build the image and then `docker-compose up`.


If you like to build it and run it at the same time then this command will be handy:

``` bash
docker-compose up --build
```

Login to the docker image and run command within the image
``` bash
docker exec -it 6e230c71e80a /bin/bash
```

` 6e230c71e80a` is the image number from `docker ps` command

------
Fro this tutorial I used this `https://bitpress.io/simple-approach-using-docker-with-php/`.

Thank you.