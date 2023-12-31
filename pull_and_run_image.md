### Running the image locally by pulling it from ECR Repository

```
aws ecr get-login-password --region "us-east-1" | docker login --username AWS --password-stdin <AWS_ACCOUNT_ID>.dkr.ecr.us-east-1.amazonaws.com
```

*Login Succeeded*

```
docker pull <AWS_ACCOUNT_ID>.dkr.ecr.us-east-1.amazonaws.com/blog-flask-app:blue
```

```
docker images
```

REPOSITORY                                                    TAG       IMAGE ID       CREATED        SIZE

<AWS_ACCOUNT_ID>.dkr.ecr.us-east-1.amazonaws.com/blog-flask-app   blue    dc740bbd7df4   26 hours ago   173MB

```
docker run -p 5000:5000 <AWS_ACCOUNT_ID>.dkr.ecr.us-east-1.amazonaws.com/blog-flask-app:blue
```

```
docker ps        
```

CONTAINER ID   IMAGE                                                              COMMAND                  CREATED          STATUS          PORTS                    NAMES

ad3616a7b99b   <AWS_ACCOUNT_ID>.dkr.ecr.us-east-1.amazonaws.com/blog-flask-app:blue   "/bin/sh -c 'flask r…"   31 seconds ago   Up 31 seconds   0.0.0.0:5000->5000/tcp   objective_faraday

```
docker kill ad3616a7b99b
docker exec -it 8ac5780306a8 /bin/bash
```
