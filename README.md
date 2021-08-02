# Containerized status monitoring server using Statping, container running on Podman

## Build Image from Containerfile
```
podman build -t container-dnsmasq .
```

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
Open at [server_ip]:8080 in your browser, credentials should be statping/statping.
