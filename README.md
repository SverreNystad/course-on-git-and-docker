# Git and Docker Course
Accompanying presentation can be found [here](https://docs.google.com/presentation/d/1haH8cLeZ95V6aTcdJPhm0mP9muZv_u7NCb_go_Od8s8/edit#slide=id.g2b9969c2c06_0_0)

## Part 1: Git

### Task 0: Initial Setup
For this workshop, you will need to have Git installed on your machine and have a GitHub account.

If you don't have git installed, follow the instructions below to install it.
* Install git on your machine
  - [Windows](https://git-scm.com/download/win)
    * Press `Win + R` then write `cmd`
    * ```cmd
        winget install --id Git.Git -e --source winget
      ```
      Or download installer from [here](https://github.com/git-for-windows/git/releases/download/v2.43.0.windows.1/Git-2.43.0-64-bit.exe)
  - [Mac](https://git-scm.com/download/mac)
    * Make sure to have brew installed if you don't have it follow [this](https://brew.sh/)
    * ```bash
      brew install git
      ``` 
  - [Linux](https://git-scm.com/download/linux)
    * You probalby allready have Git preinstalled lmao enjoy
    * If you somehow don't gave git see [here](https://git-scm.com/download/linux) for instructions for your distro

To validate that git is installed, open a terminal/cmd and write 
```bash
git --version
```
If you get a version number, you are good to go.

* Create a github account [Github](https://github.com/) if you don't have one already


### Task 1: Cloning the repository
* Clone the repository in the directory of your choosing (open a terminal/cmd in that directory)
```bash
git clone https://github.com/SverreNystad/git-course.git
```
then change to the directory `git-course`

### Task 2: Adding a file to the repository
1. Create a new file named after your first and last name in the greeting_of_cogito folder. Write a greeting message to the rest of the members.
2. Add and commit the new file to the repository:

```bash
git add .
git commit -m "feat: Add greeting from [Your Name]"
git pull
git push
```

### Task 3: Dealing with Merge conflicts
In this task you will need to merge the `feat-hello-universe` into `main` branch. 
This will cause a merge conflict that you will need to resolve.

First of all make sure both branches are in your local repository
```bash
git branch --list
```
you should have at least two branches `main` and `feat-hello-universe`

if not you can fetch the branches from the remote repository by using the following command
```bash
git fetch origin feat-hello-universe
git checkout feat-hello-universe
```

to switch back to the main branch you can use the following command
```bash
git checkout main
```

To see the difference between the two branches you can use the following command
```bash
git diff main feat-hello-universe
```

Now try to merge the `feat-hello-universe` into `main` branch and resolve the merge conflict.
```bash
git merge main feat-hello-universe
```

Feel free to use any text editor to resolve the merge conflict, after you have resolved the conflict you can add and commit the changes. (don't push the changes this time around)


## Part 2: Docker

### Task 0:
Install Docker on your machine follow the link for your OS
* [Install on Windows](https://docs.docker.com/desktop/install/windows-install/)
* [Install on Mac](https://docs.docker.com/desktop/install/mac-install/)

* [Install on Linux](https://docs.docker.com/desktop/install/linux-install/)
  * This scrip also does the trick
    ```bash
    curl -fsSL https://get.docker.com -o get-docker.sh
    sh get-docker.sh
    ```

To validate that docker is installed, open a terminal/cmd and write
```bash
docker --version
```
further more you might have to start the docker daemon (if it has not started already), by opening the docker desktop application and going through the setup.

### Task 1: Run a docker container

To run an example docker container, open a terminal/cmd and write
```bash	
docker run hello-world
```

Change to the directory `docker/hello_world` and pull and run the docker container
```bash
docker compose up
```
this container exits after completion.

For the next example change to the directory `docker/many_apps` and we will look at a more complex compose file

To run this:
```bash
docker compose up
```

If you look into it we will be deploying 3 services, check them out using the links and/or look through the compose file
- Postgres DB
- Firefox browser (browser running withing a container) [link](localhost:8091)
- Uptime kuma (a web app) [link](localhost:8090)

This time we need to turn the stack off as these applications will run continuously:
```bash	
docker compose down
```

### Task 2: Build a docker image
In the last task you shall edit the `Dockerfile` that builds a docker image that runs our hello world application.

To build the image, open a terminal/cmd and write
```bash
docker build -t hello-world .
```

To run the image, open a terminal/cmd and write
```bash
docker run hello-world
```

