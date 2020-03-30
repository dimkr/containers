FROM dimkr/c-dev:slim

ENV GOPATH /go
ENV PATH $PATH:/usr/local/go/bin:$GOPATH/bin

RUN apt-get -qq update && apt-get install wget && wget -qO- https://dl.google.com/go/go1.13.4.linux-amd64.tar.gz | tar -C /usr/local -xzf- && apt-get autoremove --purge -y wget
