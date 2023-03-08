# docker-kubernetes
docker commands:
>>> docker info
>>> docker version
>>> docker login

>>> docker run -d -p 7080:80 --name webserver nginx
{-d         detached mode
 -p         port mapping
 --name     container local given name}

>>> docker ps
{list all running containers}

>>> docker ps -a 
{-a     list all containers}

>>>docker container exec -it webserver bash
{attach a program(bash) to the container}

>>> docker stop webserver

>>> docker rm webserver
{remove container from memory}

>>> docker rmi nginx
{nginx  name of the image, not the container}

Docker Extension from Mocrosoft for VS Code:
search in the command Pallette:
>>> docker add
>>> docker build 
>>> docker run


>>> docker volume create myvol
{creates a volume}

>>> docker volume ls
{lists all volumes}

>>> docker run -d --name voltest -v myvol:/app nginx:latest
{-v myvol:/app      volume created earlier mapped to folder named "app"}

>>> docker exec -it voltest bash
>>>$ apt-get install nano
>>>$ cd app
>>>$ nano test.txt
>>>$ exit
{create a file named test.txt using bash inside the app folder and exit out of bash}

>>> docker stop voltest
>>> docker rm voltest
{stop the container and delete it}

>>> docker run -d --name voltest -v myvol:/app nginx:latest
>>> docker exec -it bash
>>>$ cd app
>>>$ ls
{create and run the container again to check if the file text.txt is present in the volume -- it is present}

>>> docker stop voltest
>>> docker rm voltest
>>> docker volume rm myvol
{stop and remove the container and then remove the volume (in that order)
this will remove the test.txt file}