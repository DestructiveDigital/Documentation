# Using the Docker environment


## Starting A Project

Each of the environments (dev, qa etc) will have it's own docker-compose.{env_name}.yaml file, in this all of the custom configuration for the application should be entered. For Wordpress the details entered into there will be propagated into wordpress.conf. In addition to the wordpress.conf there is a environment specific php.ini file, this is called either 'php.dev.ini' or 'php.qa.ini', these are used to apply additional PHP overrides in each environment.

To bring up an environment navigate to the root directory of the project in a bash shell, the root of the project should look similar to the below:

`|-- README.md
|-- config
|-- database
|-- ddenv
|-- docker-compose.dev.yaml
|-- docker-compose.qa.yaml
|-- wordpress.conf
|-- php.dev.ini
|-- php.qa.ini
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

## Accessing Logs:

With Docker container storage is ephemeral, this means that logs are ideally not written to the containers storage. For this reason the logs are streamed out to the host docker daemon. In order to view the logs from the developers host machine you can either dump the log to your project fie system or attach to the log stream. Depending on the nature of your use of the logs will dictate which is more useful at any given point.

### Attaching to the log stream

Attaching to the log stream means that you will receive new lines as they are added to the log, in order to do this use the below commands (remember to prefix the necessary bash call (e.g sh)):

`./ddenv logs`

Or to view logs for a specific service:
`./ddenv logs-wordpress`

`./ddenv logs-db`

## Dumping logs to file

When dumping to file a folder will be created in your project called logDumps, this will contain the newly dumped log files with the time stamp of the dump as there title. In order to do this use the below commands (remember to prefix the necessary bash call (e.g sh)):

`./ddenv dumpLogs`

Or to dump only a single specific container:
`./ddenv dumpLogs-wordpress`

`./ddenv dumpLogs-db`


## SSH into the containers

> This will not work on Windows, On windows use docker-compose directly.

To SSH into the containers use the below commands:

DB Mac: `sh ./ddenv ssh-db`
Wordpress Mac: `sh ./ddenv ssh-wordpress`

DB Linux: `bash ./ddenv ssh-db`
Wordpress Linux: `bash ./ddenv ssh-wordpress`