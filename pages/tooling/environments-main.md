# Environments

Project environments are managed by Docker and docker-compose. In order to simplify the movement between "dev" and "qa" environments there is a helper script that selects the appropiate docker-compose script automaticaly. This helper script is named `ddenv`. It is a bash script that passes the parameters to the apprppiate docker-compose script depending on the current environment. This script should be placed in the root of the project along with the docker-compose scripts and called from a bash terminal. See the Docker usage page for more. 
