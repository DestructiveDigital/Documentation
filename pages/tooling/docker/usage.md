# Using the Docker environment



## Starting A Project

To bring up an environment navigate to the root directory of the project in a bash shell, the root of the project should look similar to the below:

`|-- README.md
|-- config
|-- database
|-- ddenv
|-- dev.conf
|-- docker-compose.dev.yaml
|-- docker-compose.qa.yaml
|-- prod.conf
|-- public
-- qa.conf`

You will need to be using a bash shell, if you are in windows ensure that you are using git bash. To bring up the docker environment execute the bellow command:

Windows: `./ddenv up --build ` 

Mac: `sh ./ddenv up --build `

Linux: `bash ./ddenv up --build `

If you wish to use a domain in the place of local host then add a record to /etc/hosts

## Tearing Down Project

To then tear down all of the associated resources similar to the functionality of `vagrant destroy` execute:

Windows: `./ddenv down`

Mac: `sh ./ddenv down`

Linux: `bash ./ddenv down`
 

## Changing the environment

In order to switch between 'dev' and 'qa' simply change the `Environment` variable in the destructive script, calling  `./ddenv down && ./ddenv up --build` will then 
bring the newly selected environment live.

