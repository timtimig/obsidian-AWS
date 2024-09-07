# Amazon Elastic Container Service

With ECS, your containers are defined in a task definition that you use to run an individual task or a task within a service.
You can run tasks in a container service using both options: [[EC2]] (for more control) or serverless infrastructure like [[Fargate]].
If you choose EC2 you will also need to install a ECS #container_agent on EC2 instances (it's called a container instance).

To prepare your application to run on ECS, you create a task definition. The task definition is a text file, in JSON format, that describes one or more containers.

#ECS