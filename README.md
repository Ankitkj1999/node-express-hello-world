# Simple Node Express Hello World App


![localhost:3000](/public/images/localhost_3000.png?raw=true "Node & Express")

# Steps :
```
  git clone https://github.com/eMahtab/node-express-hello-world
  cd node-express-hello-world
  npm install
  npm start

  Go to localhost:3000

```  



<!-- Revious Script -->

```
name: CD Pipeline

on:
  workflow_run:
    workflows: ["CI Pipeline"]
    types:
      - completed

jobs:

  build:

    runs-on: self-hosted

    steps:
    - name: Pull Docker image
      run: docker pull ankitkj199/node-express-hello-world:latest
    - name: Delete Old docker container
      run: sudo docker rm -f cicd-pipeline-container || true
    - name: Run Docker Container
      run: sudo docker run -d -p 8080:8080 --name cicd-pipeline-container ankitkj199/node-express-hello-world


```