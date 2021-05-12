# Docker/Python Hello World #
This is a simple docker tutorial for building and running a python Hello World application. Dockerfile has been excluded for the sake of the building exercise, and application exits immediately after running the `print("Hello World!)` command.

### Prerequisites ###
- Docker Desktop
- git
- python 3
- VS Code
- VS Code Extension: Docker

## 1. Clone Repository ##
- cd to target directory
- `git clone "https://github.com/alexfricker/docker-python-hello-world.git"`
- main.py contains code that will be executed

## 2. Add Dockerfile ##
- Open VS Code
- Open directory where repo was cloned
    - if prompted, select a python interpreter version
- Press "F1" and type "docker add". Select "Docker: Add Docker Files to Workspace..."
    - Select "Python: General"
    - Select "main.py" as the entry point
    - Select "No" for including optional Docker Compose files
- Inspect generated docker files:
    - Dockerfile
        - contains specifications for docker image
    - requirements.txt
        - contains list of required python libraries

## 3. Build Docker Image ##
- Press "F1" and type "docker add". Select "Docker Images: Build Image..."
- Close terminal that was opened for build
- Open Docker extension to see new image
    - new image created under "Images" pane
    - named the same as the folder you built the files from

## 4. Run Docker Image in a Container ##
### Terminal ###
`docker run dockercshelloworld`
### Docker Desktop ###
- Open Docker Desktop
- Select "Images" to see local images (same list as VS Code)
- Hover over "dockerpythonhelloworld" and select "Run" to create and start a container with this image
    - Leave optional settings blank and select "Run"
- Examine logs (Containers > Select container name > Logs)
    - Shows "Hello World!" and container stopped after execution
- Re-run container (Click the run/play button) to see log entries for each execution

## 5. Next Steps ##
- Add a sleep command to prevent the container from immediately closing
    - `import time time.sleep(600)`
    - rebuild, re-run
    - open a CLI through Docker Desktop - ">_" icon
    - explore filesystem
- Add additional files and try to get them to copy to the container (hint: review the Dockerfile)
- Add additional code for other tasks and try to build and run
