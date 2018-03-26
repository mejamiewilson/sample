# Using the sample container

Prereq's: 
 - Docker hub account (hub.docker.com)
 - Docker host installed 
 - Make sure the docker host is running

## Make the containers

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

# Test Runs

## UI Test

Scope: creating a new 

|   |   |   |   |   |
|---|---|---|---|---|
|Create container   |   |   |   |   |
|   |   |   |   |   |
|   |   |   |   |   |


## Notes on using the UI

- Missing title on the create container page. Add "Create container" (what does droplet have?)
- Typing into the container selector calls an API on key up without merging latest results (so no 'filtering down' effect)
- Can't arrow down (i.e. type jamieatdo/ then hit the down arrow to select an entry)
- Tabbing to the next field doesn't kill the dropdown
- Hitting enter in the version field doesn't submit the modal
- The hostname is set to the be the container name (socket.gethostname() in python), UI should make it clear that it's a functional label, and not a descriptor
- The 'container name' text placeholder is too strong for a placeholder, it looks like it's already filled out
- My container looks for env variable UI to update the "Hostname:" on the page response. It's not being set 
- This might be an issue with being in a dev environment, but sometimes if i leave my container long enough, there's a 'cold start' effect where it takes 30 seconds to find the container / execute the request on port 80. Are we killing containers when they're not in use?







