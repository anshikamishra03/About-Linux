## Setup Linux Environment on Windows and MacOS
There are multiple ways to setup a Linux environment on a Windows or Mac machines such as cloud vm, wsl2, virtualbox, Hyperkit e.t.c.,. However what I would recommend is using a container as a Linux environment.

## Setup using windows
Run the command 

```wsl -- install```

Just install Docker desktop, run the below command and create linux container of any distribution without worrying about the cost and connectivity issues.

### Docker Command to Run Ubuntu Linux Container in windows host (Persistent & Long-Term)
```
docker run -dit \
  --name ubuntu-container \
  --hostname ubuntu-dev \
  --restart unless-stopped \
  --cpus="2" \
  --memory="4g" \
  --mount type=bind,source=C:/ubuntu-data,target=/data \
  -v /var/run/docker.sock:/var/run/docker.sock \
  -p 2222:22 \
  -p 8080:80 \
  --env TZ=Asia/Kolkata \
  --env LANG=en_US.UTF-8 \
  ubuntu:latest /bin/bash
```
### Docker Command to Run Ubuntu Linux Container in mac or linux host (Persistent & Long-Term)
```
docker run -dit \
  --name ubuntu-container \
  --hostname ubuntu-dev \
  --restart unless-stopped \
  --cpus="2" \
  --memory="4g" \
  --mount type=bind,source=/tmp/ubuntu-data,target=/data \
  -v /var/run/docker.sock:/var/run/docker.sock \
  -p 2222:22 \
  -p 8080:80 \
  --env TZ=Asia/Kolkata \
  --env LANG=en_US.UTF-8 \
  ubuntu:latest /bin/bash
```          
### Explanation of Each Parameter
#### Parameter 
#### Description
1. -dit	-> Runs the container in detached (-d), interactive (-i), and terminal (-t) mode.
   
2. --name ubuntu-container	->Assigns a name to the container for easy management.
   
3. --hostname - ubuntu-dev->	Sets the container’s hostname.

4. --restart unless-stopped	->Ensures the container restarts automatically unless manually stopped.

5. --cpus="2"	->Limits the container to 2 CPU cores.

6. --memory="4g"->	Allocates 4GB RAM to the container.

7. --mount type=bind,source=C:/ubuntu-data,target=/data->	Mounts a folder from Windows into the container to persist data.

8. -v /var/run/docker.sock:/var/run/docker.sock	->Allows running Docker commands inside the container (optional).

9. -p 2222:22->	Maps port 2222 on the host to 22 (SSH) inside the container.

10. -p 8080:80-> Maps port 8080 on the host to 80 (for web services).

11. --env TZ=Asia/Kolkata	->Sets the timezone (modify based on your location).

12. --env LANG=en_US.UTF-8-> Sets the language settings inside the container.

13. ubuntu:latest /bin/bash->	Uses the latest Ubuntu image and runs Bash shell.
