<h1>AIM: To find out how to create a container and deploy it in a virtual machine.</h1>

## Cloning and testing a Github repository
1. Forked from https://github.com/u1i/nodejs-api


2. This command clones the forked repository into the cloud shell virtual machine. 
```
git clone https://github.com/Gugaplex/nodejs-api
```

3. This command opens the nodejs-api folder
```
cd nodejs-api
```

4. An image is created from the dockerfile, which is the “recipe” for the docker image, using the command below.
```
docker build . -t container
```

5. These commands were done to test if the api call is running fine. 
```
docker run -d -p 8080:8080 container
```
```
curl -i http://localhost:8080/fx
```
<p align="center">
  <img src="https://raw.githubusercontent.com/Gugaplex/nodejs-api/master/Picture1.png" align="center"></img>
</p>

</br>

## Pushing a container to Docker and deploying an image in a new virtual machine
6. This creates a tag for the docker container.
```
docker tag container gugaplex/container:1
```

7. Your Docker account username and password is input in this stage to enable the container to be pushed to your docker repository.
The authentication prevents others from spamming your repository.
```
docker login
```

8. This command pushes the container to the docker repository. 
```
docker push gugaplex/container:1
``` 
<p align="center">
  <img src="https://raw.githubusercontent.com/Gugaplex/nodejs-api/master/Picture2.png"></img>
</p>

9. A new cloud shell virtual machine was run and this command was used to deploy the image.
```
docker pull gugaplex/container:1
```

10. This api was called to test if the docker image was deployed successfully. 
```
curl -i http://localhost:8080/fx
```
<p align="center">
  <img src="https://raw.githubusercontent.com/Gugaplex/nodejs-api/master/Picture3.png"></img>
</p>

