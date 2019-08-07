# SwitchEnv
SwitchEnv is a simple bash wrapper around Docker containers so that developers that need to compile or test code in different environments can easily switch between different docker containers to do their development.
## WARNING
Consider SwitchEnv in an early Alpha phase (I literally just threw this together last week!)
## Installation
Copy the `switch` script into a folder in your path (Something like ~/bin works nicely) and copy the template switchenv.conf to a new folder called `~/.switchenv`.
## Defining Environments
Currently, there are just two simple configuration parameters: `BASEMOUNTS` and `ENVIRONMENTS`
* BASEMOUNTS: This is a BASH array containing all the mounts from the underlying server that should be mounted into the Docker container. They are currently mounted in the same location as the underlying server (So an entry of "/etc/localtime" is mounted to /etc/localtime)
* ENVIRONMENTS: This is a BASH associative array that maps the environment name to the docker image associated with it. The key in the associative array is the name you'll use with the switch script to access a particular image.
