

# Specify a base image

# FROM alpine
FROM node:alpine

# where we can place our application
WORKDIR /usr/app

#Copying the package.json from the current working directory locally 
#to the current working directory of the container.
COPY ./ ./

# Install some dependencies
RUN npm install 

# Default command 
CMD ["npm", "start"]