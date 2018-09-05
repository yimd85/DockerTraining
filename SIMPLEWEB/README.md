Install docker
Create a node environment
Create a docker file

Terminal Command: 
docker build . 
Result: NPM is not found. We are seeing this error message because the docker container does not hold the npm node module
Fix: use another image other than Alpine. We went into the docker hub and used node:alpine. Alpine is the term in the docker world that means it is as small and compact as possible.


result: now we need to make sure the package.json needs to exist on the docker container. 
Fix: go to the dockerfile and copy the current working directory's package.json file to the containers working directory. In this case we added ```COPY ./ ./``` to the docker fiel

Now we would like to make a build that does not use the built image #. We would like to use the tag the image with a name so we typed in the following command on the terminal. 
```docker build -t davidyim/simpleweb .```

then we ran the image using terminal command ```docker run davidyim/simpleweb```

This will successfully run the container. However the post is not routed into the container. This is because the localhost network and the container host is seperate. We can forward the localhost network over to the container host to solve this issue.

setup port forward mage using terminal command ```docker run -p 3000:8080 davidyim/simpleweb```

first port is the local host, second is the container host

then we can navigate to local host localhost:3000 

start up a shell using terminal command ```docker run -it davidyim/simpleweb sh```

we can see the we added package.json, package-lock.json, index.js on the root directory.  In this case we added ```WORKDIR /usr/app``` to the docker file

Use the build command and port forwarding command
```docker build -t davidyim/simpleweb .```
```docker run -p 3000:8080 davidyim/simpleweb```

we can open up a new window on the terminal then use command
```docker ps``` to get the container ID, start up the shell using ```docker exec -it <ID of container> sh```