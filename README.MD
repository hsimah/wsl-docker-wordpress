# wsl-docker-wordpress
A simple boilerplate to get started with WordPress, Docker and WSL2.

## Instructions
Open folder in vs code via WSL. Reopen in container and let docker-compose build the containers, volumes and images.

### SSH Keys

Create an external volume to store ssh keys:
```
$ docker volume create --name ssh
```
Generate new ssh keys and upload to GitHub.
Add `~/.ssh/config` and enter:
```
Host github.com
  IdentityFile ~/.ssh/docker-github
```
This volume can be shared with other containers to keep development github access.

### Debugging

Create a launch.json
```
{
  // Use IntelliSense to learn about possible attributes.
  // Hover to view descriptions of existing attributes.
  // For more information, visit: https://go.microsoft.com/fwlink/?linkid=830387
  "version": "0.2.0",
  "configurations": [
    {
      "name": "Listen for XDebug",
      "type": "php",
      "request": "launch",
      "port": 9001,
      "hostname": "0.0.0.0"
    },
  ]
}
```