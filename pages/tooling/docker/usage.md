# Using the Docker environment


## Starting A Project

Each of the environments (dev, qa etc) will have it's own docker-compose.{env_name}.yaml file, in this all of the custom configuration for the application should be entered. For Wordpress the details entered into there will be propagated into wordpress.conf. 

To bring up an environment navigate to the root directory of the project in a bash shell, the root of the project should look similar to the below:

`|-- README.md
|-- config
|-- database
|-- ddenv
|-- docker-compose.dev.yaml
|-- docker-compose.qa.yaml
|-- wordpress.conf
|-- public
`

You will need to be using a bash shell, if you are in windows ensure that you are using git bash. To bring up the docker environment execute the bellow command:

Windows: `./ddenv up ` 

Mac: `sh ./ddenv up `

Linux: `bash ./ddenv up`

If you wish to use a domain in the place of local host then add a record to /etc/hosts

## Tearing Down Project

To then tear down all of the associated resources similar to the functionality of `vagrant destroy` execute:

Windows: `./ddenv down`

Mac: `sh ./ddenv down`

Linux: `bash ./ddenv down`
 

## Changing the environment

In order to switch between 'dev' and 'qa' simply change the `Environment` variable in the destructive script, calling  `./ddenv down && ./ddenv up --build` will then 
bring the newly selected environment live.

## SSH into the containers

> This will not work on Windows, On windows use docker-compose directly.

To SSH into the containers use the below commands:

DB Mac: `sh ./ddenv ssh-db`
Wordpress Mac: `sh ./ddenv ssh-wordpress`

DB Linux: `bash ./ddenv ssh-db`
Wordpress Linux: `bash ./ddenv ssh-wordpress`