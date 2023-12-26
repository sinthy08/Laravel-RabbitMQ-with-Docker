# Laravel RabbitMQ with Docker

The RabbitMQ have been implemented using CloudAMQP. The details can be found in the blog https://www.twilio.com/blog/rabbitmq-job-queues-laravel.

## Installing the project
### Setup Cloud Server
1. To setup the cloud server go to CloudAMQP and create a free account (without Credit card info). You'll find creadentials there to connect your laravel app with the cloud.
   
![image](https://github.com/sinthy08/laravel_rabbitMQ/assets/40598386/c62c3138-5074-4ed6-8ab6-c1ab2977ea28)

2. To install the project simply clone the repository and update the .env file with the proper cloud credentials.
   
![image](https://github.com/sinthy08/laravel_rabbitMQ/assets/40598386/4c8e6ffb-25c4-490a-862f-e2afb7c04f23)


### Docker Container Setup
3. Make sure your system has docker installed. Use the command below to setup the docker image for the project. (You can see this link to setup docker for any laravel project: https://github.com/iwasherefirst2/laravel-docker)
   > docker-compose up -d --build
   
   then use this command to see the created image for your project.

   > docker-compose ps

4. Make necessary changes in your .env file for docker, like- app name or DB credentials, then install the composer dependencies.

   
### Install Composer dependencies

5. Bash into your container:

> docker-compose exec app bash

6. Install composer dependencies (this may also take a moment):

> composer install

7. and finally generate a key

> php artisan key:generate

<b> Your app should now be accessible under localhost:8005 or http://127.0.0.1:8005 </b>

### App view
Go to the link localhost:8005 or http://127.0.0.1:8005 you'll see a message box like the image below:

![image](https://github.com/sinthy08/laravel_rabbitMQ/assets/40598386/b76e4b75-4caa-4583-b081-227f88273e7f)

Now, write any message here and press the 'send message' button. You can see the message from your laravel app console. Write the given command on the laravel app console to comsume the message.
Go to the console and write this commands
> sudo docker ps

see the containers running take the APP_ID of the rabbitMQ_app and run the following command

> sudo docker exec -it APP_ID bash

Then to consume the text sent from the localhost server use this command below-

> php artisan mq:consume

![image](https://github.com/sinthy08/laravel_rabbitMQ/assets/40598386/ec45b2ff-54e6-4ca1-98d1-a092996131fd)

To fully understand the code above, you will need to understand the RabbitMQ message flow. It works something like this:

![image](https://github.com/sinthy08/laravel_rabbitMQ/assets/40598386/8dca35d9-e7f7-49e9-92c9-66d25eb9b48b)
