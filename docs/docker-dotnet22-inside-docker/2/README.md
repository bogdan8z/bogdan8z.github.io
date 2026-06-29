
# Image created from ubuntu 18.04 and then added docker and .NET core sdk 2.1.200

1. Run this:

>docker build -t my-image-name .
>docker run --name test1-my-image-name -d my-image-name

2. Utils:

>docker logs <container_name>

>docker run -it <image_name> bash

>docker exec -it <container_name> bash

>docker container prune

>docker container inspect <container_name>

>docker system prune

3. More info: 

https://docs.microsoft.com/en-us/dotnet/core/tools/dotnet-install-script

https://github.com/aws/aws-codebuild-docker-images/tree/master/ubuntu/standard/3.0

https://docs.microsoft.com/en-us/dotnet/core/install/linux-ubuntu#1804-

https://www.itzgeek.com/how-tos/linux/ubuntu-how-tos/how-to-install-docker-on-ubuntu-18-04-lts-bionic-beaver.html

https://docs.microsoft.com/en-us/dotnet/core/install/linux-ubuntu
