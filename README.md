<h1>AIM: To find out how to create a container and deploy it in a virtual machine.</h1>


1. Forked from https://github.com/u1i/nodejs-api


2. ```git clone https://github.com/Gugaplex/nodejs-api```

This clones the forked repository into the cloud shell virtual machine.

3. ```cd nodejs-api```

This opens the nodejs-api folder

4. ```docker build . -t container```

Docker creates an image from the dockerfile, which is the “recipe” for the docker container.

5. ```docker run -d -p 8080:8080 container```
6. ```curl -i http://localhost:8080/fx```

Steps 5 and 6 are done to test if the api call is running fine.
<img src="https://raw.githubusercontent.com/Gugaplex/nodejs-api/master/Picture1.png"></img>

7. ```docker tag container gugaplex/container:1```

This creates a tag for the docker container

8. ```docker login```

Docker account username and password is input in this stage to enable the container to be pushed to the docker repository.

9. ```docker push gugaplex/container:1``` 

This command pushes the container to the docker repository. 
<img src="https://raw.githubusercontent.com/Gugaplex/nodejs-api/master/Picture2.png"></img>

10. ```docker pull gugaplex/container:1```

A new cloud shell virtual machine was run and this command was used to deploy the container.

11. ```curl -i http://localhost:8080/fx```

This api was called to test if the built docker container was deployed successfully.
<img src="https://raw.githubusercontent.com/Gugaplex/nodejs-api/master/Picture3.png"></img>


