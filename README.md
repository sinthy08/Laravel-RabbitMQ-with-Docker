# Laravel with RabbitMQ

The RabbitMQ have been implemented using CloudAMQP. The details can be found in the blog https://www.twilio.com/blog/rabbitmq-job-queues-laravel.

## Installing the project
### Setup Cloud Server
1. To setup the cloud server go to CloudAMQP and create a free account (without Credit card info). You'll find creadentials there to connect your laravel app with the cloud.
![image](https://github.com/sinthy08/laravel_rabbitMQ/assets/40598386/c62c3138-5074-4ed6-8ab6-c1ab2977ea28)

2. To install the project simple clone the repository and update the .env file with the proper cloud credentials.  
![image](https://github.com/sinthy08/laravel_rabbitMQ/assets/40598386/4c8e6ffb-25c4-490a-862f-e2afb7c04f23)

3. Now, use the following command-
> php artisan serve

After that go to the link and you'll see a message box like the image below:
![image](https://github.com/sinthy08/laravel_rabbitMQ/assets/40598386/b76e4b75-4caa-4583-b081-227f88273e7f)

Now, write any message here and press the 'send message' button. You can see the message from your laravel app console. Write the given command on the laravel app console to comsume the message.

> php artisan mq:consume

![image](https://github.com/sinthy08/laravel_rabbitMQ/assets/40598386/ec45b2ff-54e6-4ca1-98d1-a092996131fd)

To fully understand the code above, you will need to understand the RabbitMQ message flow. It works something like this:
![image](https://github.com/sinthy08/laravel_rabbitMQ/assets/40598386/8dca35d9-e7f7-49e9-92c9-66d25eb9b48b)
