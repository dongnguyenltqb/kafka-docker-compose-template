FROM alpine:latest
RUN apk add --update --no-cache openssh
COPY ./ssh-private-key.pem /private-key
RUN chmod 600 /private-key
ENTRYPOINT ["ssh" ,"-NTv" ,"-o","ServerAliveInterval=60","-o" ,"ExitOnForwardFailure=yes",  "-o", "StrictHostKeyChecking=no" ,"-i", "/private-key","-R","0.0.0.0:6241:kafka-ui:8080", "user@host.example.com"]
