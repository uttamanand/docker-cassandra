# docker-cassandra

# Install Cassandra as a docker container in Atomic OS.

# How to use Cassandra image

 # Starting a Cassandra instance using below command:

$ docker run --rm -v cassandra_data:/var/lib/cassandra -p 9042:9042 --name crew-cassandra -d cassandra:latest

... where -v cassandra_data:/var/lib/cassandra -: is to bind mount a volume. Means cassandra data will be stored at this location of host. It means ever if we remove the cassandra container, data will be not lost.

-p 9042:9042 -: is to bind the host and container ports respectively.

--name crew-cassandra -: the name you want to assign to your container and

-d -: Detached mode: leave the container running in the background

latest(optional) -: the tag specifying the Cassandra version you want.

# Few Other commands

docker volume ls ( To check the volume used by the cassandra container)

docker logs crew-cassandra ( To check the logs of cassandra container)

docker stats crew-cassandra ( To check the memory used by cassandra container)

docker ps ( To check the process of the cassandra Containr or any other container)

docker ps --size ( To check the size of cassandra container or any other container)

netstat -an | grep 9042 ( To check if cassandra is linked to this port)

netstat -apnt | grep 9042 ( To check if the 9042 port is open or not)

docker exec -it crew-cassandra bash ( To go inside the bash of cassandra container)
