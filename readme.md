## welcome to bogos

fluentassertions and libgit2sharp have to be added 
libgit is needed in both test and program, fluentassertions is only needed in tests

### import them using 
important to do in the correct folders

``dotnet add package LibGit2Sharp --version 0.27.0-preview-0182``

``dotnet add package FluentAssertions --version 6.8.0``
### This is the testing repository

<https://github.com/SDeLaVida/testing-for-bdsa>
---

### Docker commands 

## Persitent database 
To make your instance of postgres save data somewhere you need to make a volume that the docker container is bound to
---
``docker volume create bogos_memory``
---
This will make a volume visable on your docker desktop application. 
Then you will have to bind your container to that volume done by calling the volume name on your docker run command: 
---
``docker run -d -v bogos_memory:/shared-volume -e POSTGRES_DB=bogosdb -e POSTGRES_PASSWORD=mypassword --name bogosDB -p 5430:5432 postgres``

## Volatile database 

This is run the database without binding, meaning that killing the container will delete the data.

``docker run -d -e POSTGRES_DB=bogosdb -e POSTGRES_PASSWORD=mypassword --name bogosDB -p 5430:5432 postgres``
