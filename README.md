# Containerized status monitoring server using Statping, container running on Podman

## Build Image from Containerfile
```
podman build -t statping-jenkins .
```
choose Docker image to pull from

## Run container
```
podman run --rm -ti -p 8080:8080 -v /root/statping/:/app:z --name statping-jenkins statping/statping
```
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
