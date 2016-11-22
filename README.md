Supported tags and respective `Dockerfile` links 
* `latest` ([Dockerfile](https://github.com/keyfun/keystonejs-docker/blob/master//Dockerfile))
* `sass` ([sass/Dockerfile](https://github.com/keyfun/keystonejs-docker/blob/master/sass/Dockerfile))

### Initiative
The image is aiming to deploy keystonejs without rebuilding the image to install dependencies. It is particularly useful when the server has limited computational power, like f1-micro in google cloud.

### To use the image from scratch
1. [Generate the keystonejs project](http://keystonejs.com/getting-started/)
2. Optionally start [mongo db](https://hub.docker.com/_/mongo/)

        docker run --name your-mongo -d mongo

3. Add the mongo db settings into .env

        MONGO_URI=mongodb://mongo

4. Run the container by the following command

        docker run -p 80:3000 -it -d --link your-mongo:mongo --name keystonejs -v "$PWD":/usr/src/app keyfun/keystonejs

  alternatively if sass is enabled

        docker run -p 80:3000 -it -d --link your-mongo:mongo --name keystonejs -v "$PWD":/usr/src/app keyfun/keystonejs:sass

