## Docker Erasures::
docker stop $(docker ps -a -q)
docker rm $(docker ps -a -q)

## Backend Setup
```bash
docker build -t <IMAGE_NAME>
docker run -v <FULL_PATH>/scantron/backend/server:/api/ -v /api/node_modules -p 4000:4000 <IMAGE_NAME>
```

## Docker Setup
1. Download Docker and Docker Compose (if you're on a Mac it's included)
```bash
cd gobble
docker-compose build
docker-compose up

# if you're having trouble
docker-compose build --no-cache
docker-compose up

# or you get the bcrypt ELF error
docker ps # get <backend_id>
docker exec -it <backend_id> bash
npm uninstall bcrypt
npm install bcrypt
```

React frontend will be open on `localhost:3000` and includes hot-reloading.

Node.js Express backend will be open on `localhost:4000` and also includes hot-reloading.

### Some Tips
ctrl+c will close all the containers.
```bash
# list running containers, and find their container ids
docker ps
# run this to start an interactive Bash session to run commands inside the container
docker exec -it <container-id> bash
```


