# Containerized status monitoring server using Statping, container running on Podman

## Build Image from Containerfile
```
podman build -t statping-jenkins .
```
choose Docker image to pull from

## Run container
first, create directory for the hosted instance /root/statping/, then you should be able to run it:
```
mkdir /root/statping
podman run --rm -ti -p 8080:8080 -v /root/statping/:/app:z --name statping-jenkins statping/statping
```
if the container doesn't want to run, try changing access rights via chmod.
After first run you don't need to make a new directory every time, so just use the 'podman run' command.
## Stop container
```
podman rm -f statping-jenkins
```
## Concept
Host files are contained in /root/statping/, which translates to /app in container.

## Usage
Open at [server_ip]:8080 in your browser

### Adding targets
Scroll down to grey Dashboard button, login and go to Services->Create.

Username statping, psw the usual, ask #team-perfscale at Ansible Slack if you don't know.

## FAQ
#### My service doesn't work, even though with curl or browser it does, says something about certificates. What to do?
In the service detail, either uncheck the "Verify SSL" option or check and fill in the Use TLS Cert option.
