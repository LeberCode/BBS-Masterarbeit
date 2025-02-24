# BBS-Masterarbeit
This is the code to my artifact of my master thesis. The artifact was presented in the Brown Bag Session of adesso SE.

## How to run
Prerequisite: Node installed

1. Open Docker Desktop

- Install [Docker Desktop](https://www.docker.com/products/docker-desktop/)
- Open Docker Dektop

2. Start the server
- Change directory to server: ```cd server```
- Install libraries: ```npm install```
- start the server: ```node index```
- Server listening on port 3001
- Check if RabbitMQ is succesfully running:
  
  ![Successful terminal output](https://github.com/user-attachments/assets/80400890-e0c9-4685-bf1b-4d119cf7e90e)
  ![RabbitMQ on Docker Desktop running](https://github.com/user-attachments/assets/1bcbdc01-6d38-492d-ab8f-e91d2f4aa9c4)


3. Start the app
- Open a new terminal
- Change directory to app: ```cd app```
- Install libraries: ```npm install```
- Start the app: ```npm run start```
- App is running on http://localhost:8080

## Some error handling

#### Error on starting the server
![Bildschirmfoto 2025-02-24 um 17 28 34](https://github.com/user-attachments/assets/59b98b30-08ef-47d5-a324-bcae2568ba6e)

Before starting the server all docker container/images/networks created before for a project start have to be removed
- Delete container and image on docker desktop
- After that, delete the unused rabbitmq-network with ```docker network prune```
- if you have other unused docker networks you dont want to delete do:
  - ```docker network ls```
  - ```docker network rm [network name (probably rabbitmq-network)]```
  - start the server again with ```node index```

helps probably in any error state to remove docker image/container/network and start all over again 😃
