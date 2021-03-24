# pull official base image
FROM node:13.12.0-alpine

# set working directory
WORKDIR /app

# add `/app/node_modules/.bin` to $PATH
ENV PATH /app/node_modules/.bin:$PATH

# install app dependencies
COPY package.json ./
COPY package-lock.json ./
RUN npm install --silent
RUN npm install react-scripts@3.4.1 -g --silent

# add app
COPY . ./

# start app
CMD ["npm", "start"]

# docker build -t hellodocker:dev .
# Create .dockerignore
# docker run -it --rm -v ${PWD}:/app -v /app/node_modules -p 3001:3000  -e CHOKIDAR_USEPOLLING=true  hellodocker:dev

# -it                           starts container in interactive mode (because react-scripts exits after start up)]
# --rm                          removes the container and volumes after the container exits
# -v ${PWD}:/app                mounts the code into the container at "/app"
# -v /app/node_modules          specifying that we want to use the container version of the node_modules
# -p 3001:3000                  exposing our ports
# -e CHOKIDAR_USEPOLLING=true   basically allows for hotreloading