# Using the sample container

Prereq's: 
 - Docker hub account (hub.docker.com)
 - Docker host installed 

## Make the containers

 - Make sure the Docker host is running
 - Clone this repo, run `docker build -t samplecontainer .` 
 - To run locally, type `docker run -p 4000:80 samplecontainer`
 - Tag the container `docker tag samplecontainer <username>/samplecontainer` (i.e. `docker tag samplecontainer jamieatdo/samplecontainer`)

## Create the container repo on docker hub

 - Log into docker hub
 - "Create Repository"
 - Create a public repo called `samplecontainer`

## Push to the docker hub repo

 - To push to dockerhub, login via the terminal `docker login`
 - Run `docker push <username>/samplecontainer:latest`

## Install on Digital Ocean

 - Log in to DO
 - From the main nav, select 'Create' and 'Container'
 - Select the 'choose image' first option, and type in <username>/samplecontainer, then hit enter
 - Set an environment variable `UI` to `<username>/samplecontainer`
 - Choose a size and give it a name
 - Click Create
 - Click into the container (we should do this automatically)

## Test success

 - Copy the IPV4 address into the browser
   - Does it load a web page?
   - Does the first line have a capital W in World?
   - Does the second line contain the container name?
 - In the DO interface, Container paage
   - Can you see a set of logs? (work out what they should display)
 - In the DO interface, Container list
   - Does the date created reflect the date it was created?

