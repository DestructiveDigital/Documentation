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

Then type:`./ddenv up --build ` and to use detached mode add the `-d` detached flag `./ddenv up --build -d`.

The docker environment will now build and run.


## Tearing Down Project

To then tear down all of the associated resources similar to the functionality of `vagrant destroy` execute `./ddenv down`.

It would then be advisable to update your /etc/hosts so to route any domain to the correct location.
 

## Changing the environment

In order to switch between 'dev' and 'qa' simply change the `Environment` variable in the destructive script, calling  `./ddenv down && ./ddenv up --build` will then 
bring the newly selected environment live.

