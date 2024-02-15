# Git and Docker Course

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

To see the difference between the two branches you can use the following command
```bash
git diff main feat-hello-universe
```

Try to use git merge to merge the `feat-hello-universe` into `main` branch and resolve the merge conflict.



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

### Task 1: Run a docker container

To run an example docker container, open a terminal/cmd and write
```bash	
docker run hello-world
```

Change to the directory `docker/hello_world` and build and run the docker container
```bash
docker compose build
docker compose up
```

Remember to stop the container after you are done
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

